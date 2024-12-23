# Questionnaire JavaScript - Exercices de Codage

## 1. Manipulation de tableaux

**Question**: Écrivez une fonction qui trouve les doublons dans un tableau.
```javascript
const arr = [1, 2, 3, 2, 4, 5, 5, 6];
// Sortie attendue: [2, 5]
```

**Solution**:
```javascript
function findDuplicates(arr) {
    return [...new Set(arr.filter((item, index) => arr.indexOf(item) !== index))];
}

// Alternative avec reduce
function findDuplicatesReduce(arr) {
    return arr.reduce((acc, val, i) => {
        if (arr.indexOf(val) !== i && !acc.includes(val)) acc.push(val);
        return acc;
    }, []);
}
```

## 2. Manipulation de chaînes

**Question**: Créez une fonction qui vérifie si une chaîne est un palindrome.
```javascript
// "radar" => true
// "hello" => false
```

**Solution**:
```javascript
function isPalindrome(str) {
    str = str.toLowerCase().replace(/[^a-z0-9]/g, '');
    return str === str.split('').reverse().join('');
}

// Alternative avec boucle
function isPalindromeLoop(str) {
    str = str.toLowerCase().replace(/[^a-z0-9]/g, '');
    for (let i = 0; i < str.length / 2; i++) {
        if (str[i] !== str[str.length - 1 - i]) return false;
    }
    return true;
}
```

## 3. Gestion d'objets

**Question**: Écrivez une fonction qui aplatit un objet imbriqué.
```javascript
// Input:
const obj = {
    a: 1,
    b: { c: 2, d: { e: 3 } }
};
// Output: { 'a': 1, 'b.c': 2, 'b.d.e': 3 }
```

**Solution**:
```javascript
function flattenObject(obj, prefix = '') {
    return Object.keys(obj).reduce((acc, key) => {
        const pre = prefix.length ? prefix + '.' : '';
        
        if (typeof obj[key] === 'object' && obj[key] !== null) {
            Object.assign(acc, flattenObject(obj[key], pre + key));
        } else {
            acc[pre + key] = obj[key];
        }
        
        return acc;
    }, {});
}
```

## 4. Manipulation de nombres

**Question**: Écrivez une fonction qui convertit un nombre en notation romaine.
```javascript
// 58 => "LVIII"
// 1994 => "MCMXCIV"
```

**Solution**:
```javascript
function toRoman(num) {
    const roman = {
        M: 1000, CM: 900, D: 500, CD: 400,
        C: 100, XC: 90, L: 50, XL: 40,
        X: 10, IX: 9, V: 5, IV: 4, I: 1
    };
    
    return Object.entries(roman).reduce((result, [letter, value]) => {
        while (num >= value) {
            result += letter;
            num -= value;
        }
        return result;
    }, '');
}
```

## 5. Gestion des promesses

**Question**: Créez une fonction qui exécute des promesses en série.
```javascript
// Input: tableau de fonctions qui retournent des promesses
// Output: résultats dans l'ordre
```

**Solution**:
```javascript
async function sequentialPromises(promiseFns) {
    const results = [];
    
    for (const fn of promiseFns) {
        try {
            const result = await fn();
            results.push(result);
        } catch (error) {
            results.push(error);
        }
    }
    
    return results;
}

// Exemple d'utilisation
const promises = [
    () => new Promise(resolve => setTimeout(() => resolve(1), 1000)),
    () => new Promise(resolve => setTimeout(() => resolve(2), 500)),
    () => new Promise(resolve => setTimeout(() => resolve(3), 100))
];

// Usage
sequentialPromises(promises).then(console.log); // [1, 2, 3]
```

## 6. Algorithme de tri

**Question**: Implémentez un algorithme de tri rapide (quicksort).

**Solution**:
```javascript
function quickSort(arr) {
    if (arr.length <= 1) return arr;
    
    const pivot = arr[arr.length - 1];
    const left = [];
    const right = [];
    
    for (let i = 0; i < arr.length - 1; i++) {
        if (arr[i] < pivot) {
            left.push(arr[i]);
        } else {
            right.push(arr[i]);
        }
    }
    
    return [...quickSort(left), pivot, ...quickSort(right)];
}
```

## 7. Manipulation du DOM

**Question**: Créez une fonction qui construit un arbre DOM à partir d'un objet.
```javascript
// Input:
const tree = {
    tag: 'div',
    children: [
        { tag: 'h1', text: 'Title' },
        { tag: 'p', text: 'Paragraph' }
    ]
};
```

**Solution**:
```javascript
function createDOMTree(config) {
    if (typeof config === 'string') {
        return document.createTextNode(config);
    }
    
    const element = document.createElement(config.tag);
    
    if (config.text) {
        element.textContent = config.text;
    }
    
    if (config.children) {
        config.children.forEach(child => {
            element.appendChild(createDOMTree(child));
        });
    }
    
    return element;
}
```

## 8. Gestion de cache

**Question**: Implémentez une fonction de mémoïzation avec limite de temps.

**Solution**:
```javascript
function memoizeWithExpiry(fn, ttl) {
    const cache = new Map();
    
    return function(...args) {
        const key = JSON.stringify(args);
        const cached = cache.get(key);
        const now = Date.now();
        
        if (cached && now - cached.timestamp < ttl) {
            return cached.value;
        }
        
        const result = fn.apply(this, args);
        cache.set(key, { value: result, timestamp: now });
        return result;
    };
}

// Exemple d'utilisation
const expensiveFunction = memoizeWithExpiry((n) => {
    console.log('Calculating...');
    return n * 2;
}, 5000); // 5 secondes TTL
```

## 9. Gestionnaire d'événements personnalisé

**Question**: Créez un système d'événements personnalisé (pub/sub).

**Solution**:
```javascript
class EventEmitter {
    constructor() {
        this.events = {};
    }
    
    on(event, callback) {
        if (!this.events[event]) {
            this.events[event] = [];
        }
        this.events[event].push(callback);
        
        return () => this.off(event, callback);
    }
    
    off(event, callback) {
        if (!this.events[event]) return;
        this.events[event] = this.events[event]
            .filter(cb => cb !== callback);
    }
    
    emit(event, data) {
        if (!this.events[event]) return;
        this.events[event].forEach(callback => {
            callback(data);
        });
    }
}

// Exemple d'utilisation
const emitter = new EventEmitter();
const unsubscribe = emitter.on('test', data => console.log(data));
emitter.emit('test', 'Hello!');
unsubscribe(); // Désinscription
```

## 10. Debounce et Throttle

**Question**: Implémentez les fonctions debounce et throttle.

**Solution**:
```javascript
function debounce(fn, delay) {
    let timeoutId;
    
    return function(...args) {
        clearTimeout(timeoutId);
        
        timeoutId = setTimeout(() => {
            fn.apply(this, args);
        }, delay);
    };
}

function throttle(fn, limit) {
    let inThrottle;
    
    return function(...args) {
        if (!inThrottle) {
            fn.apply(this, args);
            inThrottle = true;
            setTimeout(() => inThrottle = false, limit);
        }
    };
}

// Exemple d'utilisation
const debouncedFn = debounce(() => console.log('Debounced'), 1000);
const throttledFn = throttle(() => console.log('Throttled'), 1000);
```

## 11. Générateur de séquences

**Question**: Créez un générateur qui produit la séquence de Fibonacci.

**Solution**:
```javascript
function* fibonacci() {
    let prev = 0, curr = 1;
    
    yield prev;
    yield curr;
    
    while (true) {
        const next = prev + curr;
        yield next;
        prev = curr;
        curr = next;
    }
}

// Utilisation
const fib = fibonacci();
for (let i = 0; i < 10; i++) {
    console.log(fib.next().value);
}
```

## 12. Gestionnaire d'état simple

**Question**: Créez un gestionnaire d'état simple avec possibilité de s'abonner aux changements.

**Solution**:
```javascript
class Store {
    constructor(initialState = {}) {
        this.state = initialState;
        this.subscribers = [];
    }
    
    getState() {
        return this.state;
    }
    
    setState(newState) {
        this.state = { ...this.state, ...newState };
        this.notify();
    }
    
    subscribe(callback) {
        this.subscribers.push(callback);
        return () => {
            this.subscribers = this.subscribers
                .filter(cb => cb !== callback);
        };
    }
    
    notify() {
        this.subscribers.forEach(callback => callback(this.state));
    }
}

// Utilisation
const store = new Store({ count: 0 });
store.subscribe(state => console.log('State updated:', state));
store.setState({ count: 1 });
```

Ces exercices couvrent différents aspects de la programmation JavaScript, de la manipulation de données aux patterns de conception. Chaque solution est accompagnée d'explications et d'exemples d'utilisation.

Voulez-vous des explications plus détaillées sur certains exercices ou d'autres types de problèmes de codage ?
