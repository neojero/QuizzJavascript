# Questionnaire de préparation TOSA JavaScript

## Fondamentaux du langage

1. **Question**: Quels sont les types de données primitifs en JavaScript ?
   **Réponse**: Il existe 7 types primitifs en JavaScript :
   - `string` (chaîne de caractères)
   - `number` (nombre)
   - `boolean` (booléen)
   - `null`
   - `undefined`
   - `symbol` (ES6+)
   - `bigint` (ES2020+)

2. **Question**: Quelle est la différence entre `==` et `===` en JavaScript ?
   **Réponse**: `==` effectue une comparaison avec conversion de type (coercition), tandis que `===` est une comparaison stricte qui vérifie à la fois la valeur et le type sans conversion.

3. **Question**: Qu'est-ce que le "hoisting" en JavaScript ?
   **Réponse**: Le hoisting est le comportement par défaut de JavaScript qui consiste à déplacer les déclarations de variables (var) et de fonctions en haut de leur portée respective avant l'exécution du code.

4. **Question**: Quelle est la différence entre `let`, `const` et `var` ?
   **Réponse**: 
   - `var` a une portée fonctionnelle et peut être redéclaré
   - `let` a une portée de bloc et peut être réassigné
   - `const` a une portée de bloc et ne peut pas être réassigné après initialisation

5. **Question**: Qu'est-ce qu'une closure en JavaScript ?
   **Réponse**: Une closure est une fonction qui a accès aux variables de sa portée externe même après que celle-ci a terminé son exécution. Elle "capture" l'environnement dans lequel elle a été créée.

## Manipulation d'objets

6. **Question**: Comment créer un objet en JavaScript ?
   **Réponse**: Il existe plusieurs façons :
   ```javascript
   // Notation littérale
   const obj1 = {};
   
   // Constructeur Object
   const obj2 = new Object();
   
   // Fonction constructeur personnalisée
   function Person(name) {
     this.name = name;
   }
   const obj3 = new Person("John");
   ```

7. **Question**: Comment accéder aux propriétés d'un objet ?
   **Réponse**: On peut accéder aux propriétés de deux façons :
   ```javascript
   const obj = { name: "John" };
   // Notation point
   console.log(obj.name);
   // Notation crochet
   console.log(obj["name"]);
   ```

8. **Question**: Qu'est-ce que le prototypage en JavaScript ?
   **Réponse**: Le prototypage est le mécanisme par lequel les objets JavaScript héritent des propriétés et méthodes d'autres objets. Chaque objet a une propriété interne [[Prototype]] qui pointe vers son prototype.

9. **Question**: Comment ajouter une méthode au prototype d'un objet ?
   **Réponse**: 
   ```javascript
   function Person(name) {
     this.name = name;
   }
   Person.prototype.sayHello = function() {
     return `Hello, I'm ${this.name}`;
   };
   ```

10. **Question**: Quelle est la différence entre `Object.create()` et le constructeur `new` ?
    **Réponse**: `Object.create()` crée un nouvel objet avec le prototype spécifié, tandis que `new` crée une instance d'une fonction constructeur et exécute le constructeur.

## Gestion des erreurs

11. **Question**: Comment gérer les erreurs en JavaScript ?
    **Réponse**: On utilise le bloc try-catch-finally :
    ```javascript
    try {
      // Code susceptible de générer une erreur
    } catch (error) {
      // Gestion de l'erreur
    } finally {
      // Code exécuté dans tous les cas
    }
    ```

12. **Question**: Comment créer une erreur personnalisée ?
    **Réponse**: 
    ```javascript
    class CustomError extends Error {
      constructor(message) {
        super(message);
        this.name = "CustomError";
      }
    }
    throw new CustomError("Message d'erreur");
    ```

13. **Question**: Qu'est-ce qu'une stack trace ?
    **Réponse**: Une stack trace est un rapport qui fournit des informations sur la séquence d'appels de fonctions qui ont mené à une erreur, incluant les numéros de ligne et les noms de fichiers.

14. **Question**: Comment déboguer une promesse rejetée ?
    **Réponse**: On peut utiliser `.catch()` ou un bloc try-catch avec async/await :
    ```javascript
    // Avec .catch()
    promise.then(data => {}).catch(error => console.error(error));
    
    // Avec async/await
    try {
      const data = await promise;
    } catch (error) {
      console.error(error);
    }
    ```

15. **Question**: Quelle est l'utilité de `window.onerror` ?
    **Réponse**: `window.onerror` est un gestionnaire d'événements global qui capture les erreurs non gérées dans le code JavaScript. Il permet de logger les erreurs et d'éviter que l'application ne plante.

## Asynchrone

16. **Question**: Qu'est-ce qu'une promesse en JavaScript ?
    **Réponse**: Une promesse est un objet qui représente la complétion ou l'échec éventuel d'une opération asynchrone. Elle peut être dans l'un des états suivants : pending, fulfilled, ou rejected.

17. **Question**: Quelle est la différence entre `.then()` et `async/await` ?
    **Réponse**: `.then()` utilise des callbacks chaînés pour gérer les promesses, tandis que `async/await` permet d'écrire du code asynchrone de manière synchrone, le rendant plus lisible et plus facile à déboguer.

18. **Question**: Comment exécuter plusieurs promesses en parallèle ?
    **Réponse**: On peut utiliser `Promise.all()`, `Promise.race()`, ou `Promise.allSettled()` :
    ```javascript
    const promises = [promise1, promise2, promise3];
    Promise.all(promises).then(results => {
      // Traitement des résultats
    });
    ```

19. **Question**: Comment annuler une requête fetch ?
    **Réponse**: On utilise l'API AbortController :
    ```javascript
    const controller = new AbortController();
    const signal = controller.signal;
    
    fetch(url, { signal })
      .then(response => response.json())
      .catch(err => {
        if (err.name === 'AbortError') {
          console.log('Fetch annulé');
        }
      });
    
    // Pour annuler
    controller.abort();
    ```

20. **Question**: Qu'est-ce que le "callback hell" et comment l'éviter ?
    **Réponse**: Le "callback hell" est une situation où le code devient difficile à lire à cause de multiples callbacks imbriqués. On peut l'éviter en utilisant des promesses, async/await, ou en modularisant le code.

## Manipulation des données

21. **Question**: Comment convertir un objet en JSON et vice-versa ?
    **Réponse**: 
    ```javascript
    // Objet vers JSON
    const jsonString = JSON.stringify(object);
    
    // JSON vers objet
    const object = JSON.parse(jsonString);
    ```

22. **Question**: Comment copier profondément un objet ?
    **Réponse**: Plusieurs méthodes sont possibles :
    ```javascript
    // Méthode 1 : JSON
    const deepCopy = JSON.parse(JSON.stringify(object));
    
    // Méthode 2 : structuredClone (moderne)
    const deepCopy = structuredClone(object);
    ```

23. **Question**: Comment utiliser les modules en JavaScript ?
    **Réponse**: 
    ```javascript
    // export.js
    export const maFonction = () => {};
    export default class MaClasse {};
    
    // import.js
    import MaClasse, { maFonction } from './export.js';
    ```

24. **Question**: Comment manipuler efficacement de grandes quantités de données ?
    **Réponse**: Utiliser des méthodes comme :
    - Pagination
    - Chunking (traitement par lots)
    - Web Workers pour le traitement en arrière-plan
    - Structures de données optimisées (Map, Set)
    - Virtualisation pour l'affichage

25. **Question**: Comment stocker des données côté client ?
    **Réponse**: Plusieurs options sont disponibles :
    - localStorage
    - sessionStorage
    - IndexedDB
    - Cookies
    - Cache API

## Communication avec le serveur

26. **Question**: Quelles sont les différentes méthodes pour faire des requêtes HTTP ?
    **Réponse**: 
    - fetch API
    - XMLHttpRequest
    - axios
    - jQuery.ajax()
    Exemple avec fetch :
    ```javascript
    fetch(url, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(data)
    });
    ```

27. **Question**: Comment gérer les en-têtes CORS ?
    **Réponse**: Les en-têtes CORS sont gérés côté serveur, mais côté client on peut configurer les requêtes :
    ```javascript
    fetch(url, {
      credentials: 'include',
      mode: 'cors',
      headers: {
        'Access-Control-Allow-Origin': '*'
      }
    });
    ```

28. **Question**: Comment implémenter une requête avec retry en cas d'échec ?
    **Réponse**: 
    ```javascript
    async function fetchWithRetry(url, options, maxRetries = 3) {
      for (let i = 0; i < maxRetries; i++) {
        try {
          return await fetch(url, options);
        } catch (error) {
          if (i === maxRetries - 1) throw error;
          await new Promise(r => setTimeout(r, 1000 * Math.pow(2, i)));
        }
      }
    }
    ```

29. **Question**: Comment gérer le cache des requêtes ?
    **Réponse**: On peut utiliser :
    - Cache API
    - Service Workers
    - Headers de cache HTTP
    ```javascript
    fetch(url, {
      cache: 'force-cache' // ou 'no-cache', 'reload', etc.
    });
    ```

30. **Question**: Comment gérer l'authentification dans les requêtes API ?
    **Réponse**: Plusieurs méthodes :
    ```javascript
    // JWT
    fetch(url, {
      headers: {
        'Authorization': `Bearer ${token}`
      }
    });
    
    // Basic Auth
    fetch(url, {
      headers: {
        'Authorization': 'Basic ' + btoa(username + ":" + password)
      }
    });
    ```

## Optimisation et performance

31. **Question**: Qu'est-ce que la délégation d'événements ?
    **Réponse**: La délégation d'événements consiste à attacher un gestionnaire d'événements à un parent plutôt qu'à chaque enfant, utilisant la propagation des événements pour gérer les événements des enfants.

32. **Question**: Comment optimiser les boucles en JavaScript ?
    **Réponse**: 
    - Éviter les modifications du DOM dans les boucles
    - Utiliser les méthodes appropriées (forEach, map, reduce)
    - Cacher la longueur du tableau dans une variable
    - Utiliser for...of pour les itérables
    - Considérer l'utilisation de Web Workers pour les calculs lourds

33. **Question**: Comment implémenter la mémoïzation ?
    **Réponse**: 
    ```javascript
    function memoize(fn) {
      const cache = new Map();
      return (...args) => {
        const key = JSON.stringify(args);
        if (cache.has(key)) return cache.get(key);
        const result = fn.apply(this, args);
        cache.set(key, result);
        return result;
      };
    }
    ```

34. **Question**: Comment éviter les fuites mémoire en JavaScript ?
    **Réponse**: 
    - Nettoyer les événements non utilisés
    - Éviter les closures inutiles
    - Utiliser WeakMap/WeakSet pour les références
    - Gérer correctement les timers et intervalles

35. **Question**: Comment optimiser le chargement des ressources ?
    **Réponse**: 
    - Utiliser lazy loading
    - Implémenter le code splitting
    - Utiliser les attributs async/defer pour les scripts
    - Optimiser les images et autres assets
    - Utiliser la compression

## Débogage et tests

36. **Question**: Quels sont les outils de débogage disponibles dans les navigateurs ?
    **Réponse**: 
    - Console (console.log, console.table, console.time)
    - Debugger
    - Points d'arrêt
    - Profiler
    - Network tab
    - Sources panel

37. **Question**: Comment écrire des tests unitaires en JavaScript ?
    **Réponse**: Exemple avec Jest :
    ```javascript
    describe('MaFonction', () => {
      test('devrait retourner la valeur attendue', () => {
        expect(maFonction(input)).toBe(expectedOutput);
      });
      
      test('devrait gérer les erreurs', () => {
        expect(() => maFonction(invalidInput)).toThrow();
      });
    });
    ```

38. **Question**: Comment déboguer une fuite mémoire ?
    **Réponse**: 
    - Utiliser Chrome DevTools Memory panel
    - Prendre des snapshots de la heap
    - Analyser les allocations
    - Utiliser Performance monitor
    - Vérifier les détachements d'événements

39. **Question**: Comment tester du code asynchrone ?
    **Réponse**: 
    ```javascript
    test('test async', async () => {
      const data = await fetchData();
      expect(data).toBeDefined();
    });
    
    // Ou avec done callback
    test('test async', done => {
      fetchData().then(data => {
        expect(data).toBeDefined();
        done();
      });
    });
    ```

40. **Question**: Comment simuler des requêtes API dans les tests ?
    **Réponse**: Utiliser des mocks :
    ```javascript
    jest.mock('fetch');
    
    beforeEach(() => {
      fetch.mockClear();
      fetch.mockImplementation(() => 
        Promise.resolve({
          json: () => Promise.resolve({ data: 'mock' })
        })
      );
    });
    ```

## Documentation et bonnes pratiques

41. **Question**: Comment documenter du code JavaScript ?
    **Réponse**: Utiliser JSDoc :
    ```javascript
    /**
     * Calcule la somme de deux nombres
     * @param {number} a - Premier nombre
     * @param {number} b -