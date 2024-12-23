# Questionnaire JavaScript - Objets et Asynchrone

## Partie 1 : Manipulation d'Objets

### Exercice 1 : Fusion d'objets profonds
**Question**: Créez une fonction qui fusionne deux objets de manière profonde (deep merge).

```javascript
// Exemple d'entrée
const obj1 = { a: 1, b: { c: 2 } };
const obj2 = { b: { d: 3 }, e: 4 };
// Sortie attendue: { a: 1, b: { c: 2, d: 3 }, e: 4 }
```

**Solution**:
```javascript
function deepMerge(obj1, obj2) {
    const result = { ...obj1 };
    
    for (const key in obj2) {
        if (obj2[key] instanceof Object && !Array.isArray(obj2[key])) {
            result[key] = deepMerge(result[key] || {}, obj2[key]);
        } else {
            result[key] = obj2[key];
        }
    }
    
    return result;
}

// Test
console.log(deepMerge(obj1, obj2));
```

### Exercice 2 : Observateur d'Objet
**Question**: Créez une fonction qui surveille les changements d'un objet et déclenche un callback quand une propriété change.

```javascript
// Exemple d'utilisation attendu:
// const user = createObservable({ name: 'John' });
// user.onChange((prop, value) => console.log(`${prop} changed to ${value}`));
```

**Solution**:
```javascript
function createObservable(target) {
    const handlers = [];
    
    return new Proxy(target, {
        set(obj, prop, value) {
            if (obj[prop] !== value) {
                obj[prop] = value;
                handlers.forEach(handler => handler(prop, value));
            }
            return true;
        },
        
        get(obj, prop) {
            if (prop === 'onChange') {
                return (handler) => handlers.push(handler);
            }
            return obj[prop];
        }
    });
}

// Test
const user = createObservable({ name: 'John' });
user.onChange((prop, value) => console.log(`${prop} changed to ${value}`));
user.name = 'Jane'; // Affiche: "name changed to Jane"
```

### Exercice 3 : Validation d'Objet
**Question**: Implémentez un système de validation d'objet avec des types et des règles personnalisées.

**Solution**:
```javascript
class ObjectValidator {
    constructor(schema) {
        this.schema = schema;
    }
    
    validate(obj) {
        const errors = [];
        
        for (const [key, rules] of Object.entries(this.schema)) {
            // Vérification de la présence
            if (rules.required && !obj.hasOwnProperty(key)) {
                errors.push(`${key} est requis`);
                continue;
            }
            
            if (obj.hasOwnProperty(key)) {
                const value = obj[key];
                
                // Vérification du type
                if (rules.type && typeof value !== rules.type) {
                    errors.push(`${key} doit être de type ${rules.type}`);
                }
                
                // Vérification des règles personnalisées
                if (rules.validate && !rules.validate(value)) {
                    errors.push(`${key} n'est pas valide`);
                }
            }
        }
        
        return {
            isValid: errors.length === 0,
            errors
        };
    }
}

// Test
const validator = new ObjectValidator({
    name: { type: 'string', required: true },
    age: { 
        type: 'number', 
        required: true,
        validate: value => value >= 0 && value <= 120 
    }
});

console.log(validator.validate({
    name: 'John',
    age: 150
}));
```

## Partie 2 : Programmation Asynchrone

### Exercice 4 : File d'attente de promesses
**Question**: Créez une classe qui gère une file d'attente de promesses avec un nombre maximum d'exécutions simultanées.

**Solution**:
```javascript
class PromiseQueue {
    constructor(concurrency = 1) {
        this.concurrency = concurrency;
        this.running = 0;
        this.queue = [];
    }
    
    add(promiseFunc) {
        return new Promise((resolve, reject) => {
            this.queue.push({ promiseFunc, resolve, reject });
            this.processQueue();
        });
    }
    
    async processQueue() {
        if (this.running >= this.concurrency || this.queue.length === 0) {
            return;
        }
        
        this.running++;
        const { promiseFunc, resolve, reject } = this.queue.shift();
        
        try {
            const result = await promiseFunc();
            resolve(result);
        } catch (error) {
            reject(error);
        } finally {
            this.running--;
            this.processQueue();
        }
    }
}

// Test
const queue = new PromiseQueue(2);
const delay = ms => new Promise(resolve => setTimeout(resolve, ms));

[1, 2, 3, 4, 5].forEach(num => {
    queue.add(() => delay(1000).then(() => console.log(num)));
});
```

### Exercice 5 : Retry avec backoff exponentiel
**Question**: Implémentez une fonction qui réessaie une opération asynchrone avec un délai croissant entre les tentatives.

**Solution**:
```javascript
async function retryWithBackoff(operation, maxRetries = 3, baseDelay = 1000) {
    let retries = 0;
    
    while (true) {
        try {
            return await operation();
        } catch (error) {
            retries++;
            
            if (retries >= maxRetries) {
                throw error;
            }
            
            const delay = baseDelay * Math.pow(2, retries - 1);
            const jitter = Math.random() * 100;
            
            await new Promise(resolve => 
                setTimeout(resolve, delay + jitter)
            );
        }
    }
}

// Test
const failingOperation = async () => {
    const random = Math.random();
    if (random > 0.1) throw new Error('Failed');
    return 'Success';
};

retryWithBackoff(failingOperation)
    .then(console.log)
    .catch(console.error);
```

### Exercice 6 : Cache asynchrone avec invalidation
**Question**: Créez un système de cache pour les résultats de promesses avec invalidation automatique après un certain temps.

**Solution**:
```javascript
class AsyncCache {
    constructor(ttl = 5000) {
        this.cache = new Map();
        this.ttl = ttl;
    }
    
    async get(key, fetchFunction) {
        const now = Date.now();
        const cached = this.cache.get(key);
        
        if (cached && now - cached.timestamp < this.ttl) {
            return cached.value;
        }
        
        const value = await fetchFunction();
        this.cache.set(key, {
            value,
            timestamp: now
        });
        
        return value;
    }
    
    invalidate(key) {
        this.cache.delete(key);
    }
    
    clear() {
        this.cache.clear();
    }
}

// Test
const cache = new AsyncCache(10000);
const fetchData = async (id) => {
    console.log('Fetching data...');
    await new Promise(resolve => setTimeout(resolve, 1000));
    return `Data for ${id}`;
};

async function test() {
    console.time('First call');
    await cache.get('test', () => fetchData(1));
    console.timeEnd('First call');
    
    console.time('Second call');
    await cache.get('test', () => fetchData(1));
    console.timeEnd('Second call');
}

test();
```

### Exercice 7 : Gestionnaire de transactions asynchrones
**Question**: Implémentez un système qui permet d'exécuter une série d'opérations asynchrones avec possibilité de rollback en cas d'erreur.

**Solution**:
```javascript
class AsyncTransaction {
    constructor() {
        this.operations = [];
        this.rollbacks = [];
    }
    
    addOperation(operation, rollback) {
        this.operations.push(operation);
        if (rollback) {
            this.rollbacks.push(rollback);
        }
    }
    
    async execute() {
        const results = [];
        
        try {
            for (let i = 0; i < this.operations.length; i++) {
                const result = await this.operations[i]();
                results.push(result);
            }
            return results;
        } catch (error) {
            // Exécuter les rollbacks en ordre inverse
            for (let i = this.rollbacks.length - 1; i >= 0; i--) {
                try {
                    await this.rollbacks[i]();
                } catch (rollbackError) {
                    console.error('Erreur pendant le rollback:', rollbackError);
                }
            }
            throw error;
        }
    }
}

// Test
const transaction = new AsyncTransaction();

transaction.addOperation(
    async () => {
        console.log('Opération 1');
        return 'result 1';
    },
    async () => console.log('Rollback 1')
);

transaction.addOperation(
    async () => {
        console.log('Opération 2');
        throw new Error('Erreur dans l\'opération 2');
    },
    async () => console.log('Rollback 2')
);

transaction.execute().catch(console.error);
```

Chaque exercice est accompagné d'une solution complète et testable. Souhaitez-vous des explications plus détaillées sur certains concepts ou des exercices supplémentaires sur des aspects spécifiques des objets ou de l'asynchrone ?

