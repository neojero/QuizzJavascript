<div align="center">
  <img
    src="./asset/logo.jpg"
    width="40%"
    height="40%"
  />
</div>

---

> [Notes]
> liste de thèmes du questionnaire :

    Syntaxe et Types de Données
    Fonctions
    Objets et Prototypes
    Manipulation du DOM
    Événements
    Asynchronisme (Promesses, Async/Await)
    Modules et Import/Export
    Gestion des Erreurs
    ES6+ (nouvelles fonctionnalités de JavaScript)
    Performance et Optimisation

---

> [!IMPORTANT]
> plusieurs réponses possible sur certaines questions

---

## Syntaxe et Types de Données

    Quelle est la différence entre let, const et var en JavaScript ?
        A) let et const sont bloqués, var est fonctionnel.
        B) let et const sont fonctionnels, var est bloqué.
        C) let et const sont globaux, var est local.
        D) let et const sont locaux, var est global.

    Comment déclarer et utiliser une variable de type string en JavaScript ?
        A) let str = "Hello";
        B) const str = 'Hello';
        C) var str = "Hello";
        D) string str = "Hello";

    Quelle est la différence entre == et === en JavaScript ?
        A) == compare la valeur, === compare la valeur et le type.
        B) == compare le type, === compare la valeur.
        C) == et === sont identiques.
        D) == compare la valeur et le type, === compare seulement la valeur.

    Comment vérifier si une variable est de type number en JavaScript ?
        A) typeof variable === 'number'
        B) variable instanceof Number
        C) variable.isNumber()
        D) Number.isNumber(variable)

    Quelle est la différence entre un array et un object en JavaScript ?
        A) Un array est une liste ordonnée, un object est une collection de paires clé-valeur.
        B) Un array est une collection de paires clé-valeur, un object est une liste ordonnée.
        C) Un array et un object sont identiques.
        D) Un array est une fonction, un object est une liste.

Fonctions

    Comment déclarer une fonction en JavaScript ?
        A) function myFunction() {}
        B) let myFunction = function() {}
        C) const myFunction = () => {}
        D) Toutes les réponses ci-dessus sont correctes.

    Qu'est-ce qu'une fonction fléchée (arrow function) et comment l'utiliser ?
        A) function arrowFunction() {}
        B) let arrowFunction = () => {}
        C) const arrowFunction = function() {}
        D) arrowFunction = () => {}

    Comment passer des paramètres par défaut à une fonction en JavaScript ?
        A) function myFunction(param = 'default') {}
        B) function myFunction(param = default) {}
        C) function myFunction(param = defaultValue) {}
        D) function myFunction(param = 'defaultValue') {}

    Qu'est-ce qu'une fonction anonyme et comment l'utiliser ?
        A) function() {}
        B) let anonymousFunction = function() {}
        C) const anonymousFunction = () => {}
        D) anonymousFunction = function() {}

    Comment utiliser la méthode apply pour appeler une fonction avec un contexte spécifique ?
        A) myFunction.apply(context, [args])
        B) myFunction.call(context, args)
        C) myFunction.bind(context, args)
        D) myFunction.context(args)

Objets et Prototypes

    Comment créer un objet en JavaScript ?
        A) let obj = {}
        B) const obj = new Object()
        C) var obj = Object.create()
        D) Toutes les réponses ci-dessus sont correctes.

    Qu'est-ce qu'un prototype en JavaScript et comment l'utiliser ?
        A) function MyObject() {} MyObject.prototype.method = function() {}
        B) let MyObject = { prototype: { method: function() {} } }
        C) const MyObject = function() { this.prototype = { method: function() {} } }
        D) var MyObject = { method: function() {} }

    Comment ajouter une méthode à un prototype d'objet ?
        A) MyObject.prototype.newMethod = function() {}
        B) MyObject.newMethod = function() {}
        C) MyObject.prototype = { newMethod: function() {} }
        D) MyObject.newMethod = new Function()

    Quelle est la différence entre Object.create et l'opérateur new ?
        A) Object.create crée un nouvel objet avec un prototype spécifié, new crée une instance d'une fonction constructeur.
        B) Object.create crée une instance d'une fonction constructeur, new crée un nouvel objet avec un prototype spécifié.
        C) Object.create et new sont identiques.
        D) Object.create est utilisé pour les objets, new est utilisé pour les fonctions.

    Comment utiliser Object.assign pour fusionner des objets ?
        A) Object.assign(target, source1, source2)
        B) Object.merge(target, source1, source2)
        C) Object.combine(target, source1, source2)
        D) Object.join(target, source1, source2)

Manipulation du DOM

    Comment sélectionner un élément par son ID en JavaScript ?
        A) document.getElementById('id')
        B) document.querySelector('#id')
        C) document.getElementByID('id')
        D) document.select('#id')

    Comment ajouter un nouvel élément au DOM ?
        A) document.createElement('element')
        B) document.append('element')
        C) document.addElement('element')
        D) document.insert('element')

    Comment modifier le contenu textuel d'un élément ?
        A) element.textContent = 'new text'
        B) element.innerText = 'new text'
        C) element.setText('new text')
        D) element.content = 'new text'

    Comment ajouter un écouteur d'événement à un élément ?
        A) element.addEventListener('event', callback)
        B) element.addListener('event', callback)
        C) element.on('event', callback)
        D) element.listen('event', callback)

    Comment supprimer un élément du DOM ?
        A) element.remove()
        B) element.delete()
        C) element.parentNode.removeChild(element)
        D) element.destroy()

Événements

    Comment ajouter un écouteur d'événement à un bouton en JavaScript ?
        A) button.addEventListener('click', callback)
        B) button.onclick = callback
        C) button.click(callback)
        D) Toutes les réponses ci-dessus sont correctes.

    Quelle est la différence entre addEventListener et onclick ?
        A) addEventListener permet d'ajouter plusieurs écouteurs, onclick remplace l'écouteur existant.
        B) addEventListener remplace l'écouteur existant, onclick permet d'ajouter plusieurs écouteurs.
        C) addEventListener et onclick sont identiques.
        D) addEventListener est utilisé pour les événements, onclick est utilisé pour les fonctions.

    Comment empêcher le comportement par défaut d'un événement ?
        A) event.preventDefault()
        B) event.stopDefault()
        C) event.prevent()
        D) event.defaultPrevent()

    Comment arrêter la propagation d'un événement ?
        A) event.stopPropagation()
        B) event.stopBubbling()
        C) event.halt()
        D) event.propagationStop()

    Comment déléguer des événements en JavaScript ?
        A) parent.addEventListener('event', callback)
        B) parent.delegate('event', callback)
        C) parent.on('event', callback)
        D) parent.listen('event', callback)

Asynchronisme (Promesses, Async/Await)

    Qu'est-ce qu'une promesse en JavaScript et comment l'utiliser ?
        A) let promise = new Promise((resolve, reject) => {})
        B) let promise = Promise.create((resolve, reject) => {})
        C) let promise = new Promise((resolve, reject))
        D) let promise = Promise.new((resolve, reject) => {})

    Comment utiliser async et await pour gérer des opérations asynchrones ?
        A) async function myFunction() { await promise; }
        B) function myFunction() { async await promise; }
        C) async function myFunction() { return await promise; }
        D) function myFunction() { return async await promise; }

    Quelle est la différence entre Promise.all et Promise.race ?
        A) Promise.all attend que toutes les promesses soient résolues, Promise.race attend que la première promesse soit résolue.
        B) Promise.all attend que la première promesse soit résolue, Promise.race attend que toutes les promesses soient résolues.
        C) Promise.all et Promise.race sont identiques.
        D) Promise.all est utilisé pour les promesses, Promise.race est utilisé pour les fonctions.

    Comment gérer les erreurs avec async et await ?
        A) try { await promise; } catch (error) {}
        B) async { await promise; } catch (error) {}
        C) try { return await promise; } catch (error) {}
        D) async { return await promise; } catch (error) {}

    Comment créer une promesse qui se résout après un certain délai ?
        A) new Promise(resolve => setTimeout(resolve, 1000))
        B) Promise.delay(1000)
        C) new Promise(resolve => setTimeout(() => resolve(), 1000))
        D) Promise.timeout(1000)

Modules et Import/Export

    Comment exporter une fonction depuis un module en JavaScript ?
        A) export function myFunction() {}
        B) module.exports = myFunction
        C) export myFunction = function() {}
        D) exports.myFunction = function() {}

    Comment importer une fonction depuis un module en JavaScript ?
        A) import { myFunction } from 'module'
        B) const myFunction = require('module')
        C) import myFunction from 'module'
        D) let myFunction = import('module')

    Quelle est la différence entre export default et export nommé ?
        A) export default exporte une seule valeur par défaut, export nommé exporte plusieurs valeurs.
        B) export default exporte plusieurs valeurs, export nommé exporte une seule valeur par défaut.
        C) export default et export nommé sont identiques.
        D) export default est utilisé pour les fonctions, export nommé est utilisé pour les variables.

    Comment utiliser des modules ES6 dans un projet JavaScript ?
        A) import 'module'
        B) require('module')
        C) import * as module from 'module'
        D) const module = import('module')

    Comment gérer les dépendances avec des modules en JavaScript ?
        A) import { dependency } from 'module'
        B) const dependency = require('module')
        C) import dependency from 'module'
        D) let dependency = import('module')

Gestion des Erreurs

    Comment utiliser try, catch et finally pour gérer les erreurs en JavaScript ?
        A) try { code } catch (error) { handleError } finally { cleanup }
        B) try { code } catch (error) { handleError }
        C) try { code } finally { cleanup }
        D) catch (error) { handleError } finally { cleanup }

    Qu'est-ce qu'une erreur de référence (ReferenceError) et comment la gérer ?
        A) Une erreur qui se produit lorsqu'une variable n'est pas définie.
        B) Une erreur qui se produit lorsqu'une fonction n'est pas définie.
        C) Une erreur qui se produit lorsqu'un objet n'est pas défini.
        D) Une erreur qui se produit lorsqu'une méthode n'est pas définie.

    Comment lancer une erreur personnalisée en JavaScript ?
        A) throw new Error('message')
        B) throw 'message'
        C) throw new Exception('message')
        D) throw new CustomError('message')

    Comment gérer les erreurs asynchrones avec async et await ?
        A) try { await promise; } catch (error) {}
        B) async { await promise; } catch (error) {}
        C) try { return await promise; } catch (error) {}
        D) async { return await promise; } catch (error) {}

    Comment utiliser console.error pour afficher des messages d'erreur ?
        A) console.error('message')
        B) console.log('error: message')
        C) console.warn('message')
        D) console.debug('message')

ES6+ (nouvelles fonctionnalités de JavaScript)

    Qu'est-ce que la déstructuration en JavaScript et comment l'utiliser ?
        A) const { a, b } = obj
        B) const [a, b] = array
        C) const { a, b } = array
        D) const [a, b] = obj

    Comment utiliser les littéraux de modèle (template literals) en JavaScript ?
        A) const str = `Hello ${name}`
        B) const str = "Hello ${name}"
        C) const str = 'Hello ${name}'
        D) const str = "Hello " + name

    Qu'est-ce qu'une classe en JavaScript et comment l'utiliser ?
        A) class MyClass {}
        B) function MyClass() {}
        C) const MyClass = class {}
        D) let MyClass = class {}

    Comment utiliser les paramètres rest et spread en JavaScript ?
        A) function myFunction(...args) {}
        B) function myFunction(args...) {}
        C) function myFunction(args) {}
        D) function myFunction(...rest) {}

    Qu'est-ce que le let et const et comment les utiliser ?
        A) let est utilisé pour les variables mutables, const pour les variables immuables.
        B) let est utilisé pour les variables immuables, const pour les variables mutables.
        C) let et const sont identiques.
        D) let est utilisé pour les fonctions, const pour les objets.

Performance et Optimisation

    Comment optimiser les boucles en JavaScript ?
        A) Utiliser des boucles for au lieu de forEach.
        B) Utiliser des boucles while au lieu de for.
        C) Utiliser des boucles forEach au lieu de for.
        D) Utiliser des boucles do...while au lieu de for.

    Qu'est-ce que le garbage collection en JavaScript et comment l'optimiser ?
        A) Libérer manuellement la mémoire en utilisant delete.
        B) Utiliser des variables locales au lieu de variables globales.
        C) Utiliser des objets immuables.
        D) Utiliser des fonctions pures.

    Comment utiliser requestAnimationFrame pour des animations fluides ?
        A) requestAnimationFrame(callback)
        B) setInterval(callback, 16)
        C) setTimeout(callback, 16)
        D) animateFrame(callback)

    Comment minimiser le reflow et le repaint en JavaScript ?
        A) Modifier le DOM en dehors du flux de rendu.
        B) Utiliser des styles inline.
        C) Utiliser des classes CSS.
        D) Utiliser des animations CSS.

    Comment utiliser les Web Workers pour des tâches intensives ?
        A) const worker = new Worker('worker.js')
        B) const worker = new Thread('worker.js')
        C) const worker = new Task('worker.js')
        D) const worker = new Process('worker.js')

Questions de Code

    Écrivez une fonction qui prend un tableau de nombres et retourne la somme de tous les éléments.

function sumArray(arr) {
  // Votre code ici
}

console.log(sumArray([1, 2, 3, 4, 5])); // Doit afficher 15

    Écrivez une fonction fléchée qui prend deux nombres et retourne leur produit.

const multiply = (a, b) => {
  // Votre code ici
};

console.log(multiply(3, 4)); // Doit afficher 12

    Écrivez une fonction qui utilise Object.assign pour fusionner deux objets.

const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

function mergeObjects(obj1, obj2) {
  // Votre code ici
}

console.log(mergeObjects(obj1, obj2)); // Doit afficher { a: 1, b: 3, c: 4 }

    Écrivez une fonction qui ajoute un écouteur d'événement à un bouton et affiche un message lorsque le bouton est cliqué.

function addClickListener(button) {
  // Votre code ici
}

const button = document.createElement('button');
button.textContent = 'Click me';
document.body.appendChild(button);
addClickListener(button);

    Écrivez une fonction qui utilise async et await pour attendre une seconde avant de retourner un message.

async function delayMessage() {
  // Votre code ici
}

delayMessage().then(message => console.log(message)); // Doit afficher "Message after 1 second" a

Bases de JavaScript

    Quelle est la différence entre let, const et var en JavaScript ?
        A) let et const sont bloqués, var est fonctionnel.
        B) let et const sont fonctionnels, var est bloqué.
        C) let et const sont globaux, var est local.
        D) let et const sont locaux, var est global.

    Comment déclarer et utiliser une variable de type string en JavaScript ?
        A) let str = "Hello";
        B) const str = 'Hello';
        C) var str = "Hello";
        D) string str = "Hello";

    Quelle est la différence entre == et === en JavaScript ?
        A) == compare la valeur, === compare la valeur et le type.
        B) == compare le type, === compare la valeur.
        C) == et === sont identiques.
        D) == compare la valeur et le type, === compare seulement la valeur.

    Comment vérifier si une variable est de type number en JavaScript ?
        A) typeof variable === 'number'
        B) variable instanceof Number
        C) variable.isNumber()
        D) Number.isNumber(variable)

    Quelle est la différence entre un array et un object en JavaScript ?
        A) Un array est une liste ordonnée, un object est une collection de paires clé-valeur.
        B) Un array est une collection de paires clé-valeur, un object est une liste ordonnée.
        C) Un array et un object sont identiques.
        D) Un array est une fonction, un object est une liste.

    Comment déclarer une fonction en JavaScript ?
        A) function myFunction() {}
        B) let myFunction = function() {}
        C) const myFunction = () => {}
        D) Toutes les réponses ci-dessus sont correctes.

    Qu'est-ce qu'une fonction fléchée (arrow function) et comment l'utiliser ?
        A) function arrowFunction() {}
        B) let arrowFunction = () => {}
        C) const arrowFunction = function() {}
        D) arrowFunction = () => {}

    Comment passer des paramètres par défaut à une fonction en JavaScript ?
        A) function myFunction(param = 'default') {}
        B) function myFunction(param = default) {}
        C) function myFunction(param = defaultValue) {}
        D) function myFunction(param = 'defaultValue') {}

    Qu'est-ce qu'une fonction anonyme et comment l'utiliser ?
        A) function() {}
        B) let anonymousFunction = function() {}
        C) const anonymousFunction = () => {}
        D) anonymousFunction = function() {}

    Comment utiliser la méthode apply pour appeler une fonction avec un contexte spécifique ?
        A) myFunction.apply(context, [args])
        B) myFunction.call(context, args)
        C) myFunction.bind(context, args)
        D) myFunction.context(args)

Manipulation du DOM

    Comment sélectionner un élément par son ID en JavaScript ?
        A) document.getElementById('id')
        B) document.querySelector('#id')
        C) document.getElementByID('id')
        D) document.select('#id')

    Comment ajouter un nouvel élément au DOM ?
        A) document.createElement('element')
        B) document.append('element')
        C) document.addElement('element')
        D) document.insert('element')

    Comment modifier le contenu textuel d'un élément ?
        A) element.textContent = 'new text'
        B) element.innerText = 'new text'
        C) element.setText('new text')
        D) element.content = 'new text'

    Comment ajouter un écouteur d'événement à un élément ?
        A) element.addEventListener('event', callback)
        B) element.addListener('event', callback)
        C) element.on('event', callback)
        D) element.listen('event', callback)

    Comment supprimer un élément du DOM ?
        A) element.remove()
        B) element.delete()
        C) element.parentNode.removeChild(element)
        D) element.destroy()

    Comment ajouter un écouteur d'événement à un bouton en JavaScript ?
        A) button.addEventListener('click', callback)
        B) button.onclick = callback
        C) button.click(callback)
        D) Toutes les réponses ci-dessus sont correctes.

    Quelle est la différence entre addEventListener et onclick ?
        A) addEventListener permet d'ajouter plusieurs écouteurs, onclick remplace l'écouteur existant.
        B) addEventListener remplace l'écouteur existant, onclick permet d'ajouter plusieurs écouteurs.
        C) addEventListener et onclick sont identiques.
        D) addEventListener est utilisé pour les événements, onclick est utilisé pour les fonctions.

    Comment empêcher le comportement par défaut d'un événement ?
        A) event.preventDefault()
        B) event.stopDefault()
        C) event.prevent()
        D) event.defaultPrevent()

    Comment arrêter la propagation d'un événement ?
        A) event.stopPropagation()
        B) event.stopBubbling()
        C) event.halt()
        D) event.propagationStop()

    Comment déléguer des événements en JavaScript ?
        A) parent.addEventListener('event', callback)
        B) parent.delegate('event', callback)
        C) parent.on('event', callback)
        D) parent.listen('event', callback)

Promesses

    Qu'est-ce qu'une promesse en JavaScript et comment l'utiliser ?
        A) let promise = new Promise((resolve, reject) => {})
        B) let promise = Promise.create((resolve, reject) => {})
        C) let promise = new Promise((resolve, reject))
        D) let promise = Promise.new((resolve, reject) => {})

    Comment utiliser async et await pour gérer des opérations asynchrones ?
        A) async function myFunction() { await promise; }
        B) function myFunction() { async await promise; }
        C) async function myFunction() { return await promise; }
        D) function myFunction() { return async await promise; }

    Quelle est la différence entre Promise.all et Promise.race ?
        A) Promise.all attend que toutes les promesses soient résolues, Promise.race attend que la première promesse soit résolue.
        B) Promise.all attend que la première promesse soit résolue, Promise.race attend que toutes les promesses soient résolues.
        C) Promise.all et Promise.race sont identiques.
        D) Promise.all est utilisé pour les promesses, Promise.race est utilisé pour les fonctions.

    Comment gérer les erreurs avec async et await ?
        A) try { await promise; } catch (error) {}
        B) async { await promise; } catch (error) {}
        C) try { return await promise; } catch (error) {}
        D) async { return await promise; } catch (error) {}

    Comment créer une promesse qui se résout après un certain délai ?
        A) new Promise(resolve => setTimeout(resolve, 1000))
        B) Promise.delay(1000)
        C) new Promise(resolve => setTimeout(() => resolve(), 1000))
        D) Promise.timeout(1000)

    Comment utiliser Promise.all pour attendre plusieurs promesses ?
        A) Promise.all([promise1, promise2]).then(results => {})
        B) Promise.all([promise1, promise2]).catch(error => {})
        C) Promise.all([promise1, promise2]).finally(() => {})
        D) Promise.all([promise1, promise2]).then(results => {}).catch(error => {})

    Comment utiliser Promise.race pour obtenir le résultat de la première promesse résolue ?
        A) Promise.race([promise1, promise2]).then(result => {})
        B) Promise.race([promise1, promise2]).catch(error => {})
        C) Promise.race([promise1, promise2]).finally(() => {})
        D) Promise.race([promise1, promise2]).then(result => {}).catch(error => {})

    Comment chaîner des promesses en JavaScript ?
        A) promise.then(result => {}).then(result => {}).catch(error => {})
        B) promise.then(result => {}).catch(error => {}).then(result => {})
        C) promise.catch(error => {}).then(result => {}).then(result => {})
        D) promise.then(result => {}).catch(error => {}).finally(() => {})

    Comment utiliser Promise.resolve pour créer une promesse résolue ?
        A) Promise.resolve(value)
        B) Promise.resolve(value).then(result => {})
        C) Promise.resolve(value).catch(error => {})
        D) Promise.resolve(value).finally(() => {})

    Comment utiliser Promise.reject pour créer une promesse rejetée ?
        A) Promise.reject(reason)
        B) Promise.reject(reason).then(result => {})
        C) Promise.reject(reason).catch(error => {})
        D) Promise.reject(reason).finally(() => {})

Questions de Code

    Écrivez une fonction qui prend un tableau de nombres et retourne la somme de tous les éléments.

function sumArray(arr) {
  return arr.reduce((acc, val) => acc + val, 0);
}

console.log(sumArray([1, 2, 3, 4, 5])); // Doit afficher 15

    Écrivez une fonction fléchée qui prend deux nombres et retourne leur produit.

const multiply = (a, b) => a * b;

console.log(multiply(3, 4)); // Doit afficher 12

    Écrivez une fonction qui utilise Object.assign pour fusionner deux objets.

const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

function mergeObjects(obj1, obj2) {
  return Object.assign({}, obj1, obj2);
}

console.log(mergeObjects(obj1, obj2)); // Doit afficher { a: 1, b: 3, c: 4 }

    Écrivez une fonction qui ajoute un écouteur d'événement à un bouton et affiche un message lorsque le bouton est cliqué.

function addClickListener(button) {
  button.addEventListener('click', () => {
    console.log('Button clicked!');
  });
}

const button = document.createElement('button');
button.textContent = 'Click me';
document.body.appendChild(button);
addClickListener(button);

    Écrivez une fonction qui utilise async et await pour attendre une seconde avant de retourner un message.

async function delayMessage() {
  await new Promise(resolve => setTimeout(resolve, 1000));
  return 'Message after 1 second';
}

delayMessage().then(message => console.log(message)); // Doit afficher "Message after 1 second" après 1 seconde

    Écrivez une fonction qui utilise Promise.all pour attendre plusieurs promesses et retourner leurs résultats.

function waitAllPromises() {
  const promise1 = new Promise(resolve => setTimeout(() => resolve('Promise 1'), 1000));
  const promise2 = new Promise(resolve => setTimeout(() => resolve('Promise 2'), 2000));

  return Promise.all([promise1, promise2]);
}

waitAllPromises().then(results => console.log(results)); // Doit afficher ["Promise 1", "Promise 2"] après 2 secondes

    Écrivez une fonction qui utilise Promise.race pour obtenir le résultat de la première promesse résolue.

function waitFirstPromise() {
  const promise1 = new Promise(resolve => setTimeout(() => resolve('Promise 1'), 1000));
  const promise2 = new Promise(resolve => setTimeout(() => resolve('Promise 2'), 2000));

  return Promise.race([promise1, promise2]);
}

waitFirstPromise().then(result => console.log(result)); // Doit afficher "Promise 1" après 1 seconde

    Écrivez une fonction qui utilise Promise.resolve pour créer une promesse résolue.

function createResolvedPromise(value) {
  return Promise.resolve(value);
}

createResolvedPromise('Resolved').then(result => console.log(result)); // Doit afficher "Resolved"

    Écrivez une fonction qui utilise Promise.reject pour créer une promesse rejetée.

function createRejectedPromise(reason) {
  return Promise.reject(reason);
}

createRejectedPromise('Rejected').catch(error => console.log(error)); // Doit afficher "Rejected"

    Écrivez une fonction qui chaîne plusieurs promesses et retourne le résultat final.

function chainPromises() {
  return new Promise(resolve => setTimeout(() => resolve('First'), 1000))
    .then(result => {
      console.log(result);
      return new Promise(resolve => setTimeout(() => resolve('Second'), 1000));
    })
    .then(result => {
      console.log(result);
      return 'Final Result';
    });
}

chainPromises().then(result => console.log(result)); // Doit afficher "First" après 1 seconde, "S