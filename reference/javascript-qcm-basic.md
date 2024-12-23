# QCM JavaScript - Fondamentaux et Syntaxe

## Variables et Types de Données

1. **Quelle déclaration crée une variable qui ne peut pas être réassignée ?**
   - a) `var x = 5;`
   - b) `let x = 5;`
   - c) `const x = 5;` ✓
   - d) `variable x = 5;`

2. **Quel est le résultat de `typeof null` ?**
   - a) "null"
   - b) "undefined"
   - c) "object" ✓
   - d) "boolean"

3. **Comment déclarer correctement une chaîne de caractères ?**
   - a) 'Hello World' ✓
   - b) "Hello World" ✓
   - c) `Hello World` ✓
   - d) Hello World

4. **Quel est le résultat de `3 + "2"` ?**
   - a) 5
   - b) "32" ✓
   - c) 32
   - d) "5"

5. **Quelle méthode convertit une chaîne en nombre ?**
   - a) `Number("123")` ✓
   - b) `parseInt("123")` ✓
   - c) `+"123"` ✓
   - d) `"123".toNumber()`

## Opérateurs et Comparaisons

6. **Quel opérateur vérifie l'égalité sans conversion de type ?**
   - a) `==`
   - b) `===` ✓
   - c) `=`
   - d) `!=`

7. **Que renvoie `5 == "5"` ?**
   - a) true ✓
   - b) false
   - c) undefined
   - d) error

8. **Quel est le résultat de `10 + true` ?**
   - a) "10true"
   - b) 11 ✓
   - c) 10
   - d) error

9. **Comment vérifier si une variable est undefined ?**
   - a) `variable == undefined`
   - b) `typeof variable === "undefined"` ✓
   - c) `variable === null`
   - d) `isUndefined(variable)`

10. **Que renvoie l'opérateur `&&` ?**
    - a) Toujours un booléen
    - b) La première valeur falsy ou la dernière valeur ✓
    - c) Toujours true ou false
    - d) La première valeur

## Tableaux

11. **Comment ajouter un élément à la fin d'un tableau ?**
    - a) `array.push(element)` ✓
    - b) `array.add(element)`
    - c) `array.append(element)`
    - d) `array[array.length] = element` ✓

12. **Quelle méthode supprime le premier élément d'un tableau ?**
    - a) `shift()` ✓
    - b) `unshift()`
    - c) `pop()`
    - d) `delete()`

13. **Comment créer une copie d'un tableau ?**
    - a) `[...array]` ✓
    - b) `array.slice()` ✓
    - c) `array.copy()`
    - d) `Array.from(array)` ✓

14. **Quelle méthode transforme un tableau en chaîne ?**
    - a) `toString()`
    - b) `join()` ✓
    - c) `concat()`
    - d) `stringify()`

15. **Comment vérifier si une variable est un tableau ?**
    - a) `typeof arr === "array"`
    - b) `Array.isArray(arr)` ✓
    - c) `arr instanceof Array` ✓
    - d) `arr.isArray()`

## Fonctions

16. **Quelle est la syntaxe correcte d'une fonction fléchée ?**
    - a) `const f = () => {}` ✓
    - b) `const f = => {}`
    - c) `const f => () {}`
    - d) `function => () {}`

17. **Comment déclarer une fonction avec paramètres par défaut ?**
    - a) `function f(a = 1) {}` ✓
    - b) `function f(a || 1) {}`
    - c) `function f(a default 1) {}`
    - d) `function f(a : 1) {}`

18. **Quelle est la différence entre une déclaration et une expression de fonction ?**
    - a) Il n'y en a pas
    - b) Le hoisting ✓
    - c) La performance
    - d) La syntaxe uniquement

19. **Comment appeler une fonction immédiatement après sa définition (IIFE) ?**
    - a) `function(){}()`
    - b) `(function(){})()` ✓
    - c) `function{}()`
    - d) `[function(){}]()`

20. **Que fait `return` dans une fonction ?**
    - a) Termine la fonction ✓
    - b) Renvoie undefined
    - c) Continue l'exécution
    - d) Arrête le programme

## Objets

21. **Comment accéder à une propriété d'objet ?**
    - a) `obj.property` ✓
    - b) `obj["property"]` ✓
    - c) `obj->property`
    - d) `obj::property`

22. **Comment créer un objet ?**
    - a) `let obj = {}` ✓
    - b) `let obj = new Object()` ✓
    - c) `let obj = Object.create(null)` ✓
    - d) `let obj = Object()`

23. **Comment supprimer une propriété d'un objet ?**
    - a) `delete obj.prop` ✓
    - b) `obj.prop = null`
    - c) `remove obj.prop`
    - d) `obj.prop.delete()`

24. **Quelle méthode renvoie les clés d'un objet ?**
    - a) `Object.keys(obj)` ✓
    - b) `obj.keys()`
    - c) `Object.getKeys(obj)`
    - d) `obj.getKeys()`

25. **Comment vérifier si une propriété existe dans un objet ?**
    - a) `"prop" in obj` ✓
    - b) `obj.hasOwnProperty("prop")` ✓
    - c) `obj.contains("prop")`
    - d) `Object.has(obj, "prop")`

## Structures de contrôle

26. **Quelle est la syntaxe correcte pour une boucle for ?**
    - a) `for (i = 0; i < 5; i++)` ✓
    - b) `for (i < 5; i++)`
    - c) `for (i = 0 to 5)`
    - d) `for (i = 0; i++; i < 5)`

27. **Comment écrire une condition if-else ?**
    - a) `if (x > 0) {} else {}` ✓
    - b) `if x > 0 {} else {}`
    - c) `if (x > 0) then {} else {}`
    - d) `if x > 0: else:`

28. **Quelle boucle s'exécute au moins une fois ?**
    - a) `while`
    - b) `do...while` ✓
    - c) `for`
    - d) `foreach`

29. **Comment parcourir un objet ?**
    - a) `for...in` ✓
    - b) `for...of`
    - c) `forEach`
    - d) `while`

30. **Quelle est la syntaxe du switch ?**
    - a) `switch(x) { case 1: break; }` ✓
    - b) `switch(x) { case: 1; break; }`
    - c) `switch x { case 1 break }`
    - d) `switch(x) case 1: break;`

## Gestion des erreurs

31. **Comment capturer une erreur ?**
    - a) `try {} catch(e) {}` ✓
    - b) `try {} except(e) {}`
    - c) `catch {} try {}`
    - d) `error {} catch {}`

32. **Comment lancer une erreur ?**
    - a) `throw new Error()` ✓
    - b) `raise Error`
    - c) `new Error()`
    - d) `error()`

33. **Que fait finally dans un bloc try-catch ?**
    - a) S'exécute toujours ✓
    - b) S'exécute si pas d'erreur
    - c) S'exécute si erreur
    - d) Optional

## DOM et Événements

34. **Comment sélectionner un élément par son ID ?**
    - a) `document.getElementById("id")` ✓
    - b) `document.getElement("id")`
    - c) `document.findById("id")`
    - d) `getElementById("id")`

35. **Comment ajouter un écouteur d'événements ?**
    - a) `element.addEventListener()` ✓
    - b) `element.attachEvent()`
    - c) `element.addEvent()`
    - d) `element.on()`

## Chaînes de caractères

36. **Comment convertir une chaîne en majuscules ?**
    - a) `str.toUpperCase()` ✓
    - b) `str.uppercase()`
    - c) `str.toUpper()`
    - d) `str.upper()`

37. **Quelle méthode trouve la position d'une sous-chaîne ?**
    - a) `indexOf()` ✓
    - b) `search()` ✓
    - c) `find()`
    - d) `position()`

## Méthodes de tableau

38. **Comment filtrer un tableau ?**
    - a) `array.filter()` ✓
    - b) `array.select()`
    - c) `array.where()`
    - d) `array.find()`

39. **Quelle méthode transforme chaque élément d'un tableau ?**
    - a) `map()` ✓
    - b) `forEach()`
    - c) `transform()`
    - d) `convert()`

40. **Comment trier un tableau ?**
    - a) `sort()` ✓
    - b) `order()`
    - c) `orderBy()`
    - d) `arrange()`

## ES6+ Features

41. **Qu'est-ce que la déstructuration ?**
    - a) `const {a, b} = obj` ✓
    - b) `const [a, b] = array` ✓
    - c) `const {obj} = a, b`
    - d) `const (a, b) = obj`

42. **Comment utiliser le spread operator ?**
    - a) `...array` ✓
    - b) `*array`
    - c) `..array`
    - d) `spread(array)`

43. **Comment déclarer une classe ?**
    - a) `class Name {}` ✓
    - b) `class = Name {}`
    - c) `function class Name {}`
    - d) `new class Name {}`

44. **Comment utiliser l'opérateur nullish coalescing ?**
    - a) `a ?? b` ✓
    - b) `a || b`
    - c) `a ?= b`
    - d) `a ?: b`

45. **Comment utiliser l'opérateur optional chaining ?**
    - a) `obj?.prop` ✓
    - b) `obj??prop`
    - c) `obj->prop`
    - d) `obj|prop`

## Debug

46. **Comment afficher une valeur dans la console ?**
    - a) `console.log()` ✓
    - b) `print()`
    - c) `debug()`
    - d) `log()`

47. **Comment mettre un point d'arrêt dans le code ?**
    - a) `debugger;` ✓
    - b) `break;`
    - c) `debug;`
    - d) `stop;`

48. **Comment vérifier le type d'une variable ?**
    - a) `typeof variable` ✓
    - b) `typeOf(variable)`
    - c) `variable.type`
    - d) `type(variable)`

49. **Comment mesurer le temps d'exécution ?**
    - a) `console.time()` ✓
    - b) `performance.now()` ✓
    - c) `timer()`
    - d) `time()`

50. **Comment formater un nombre avec 2 décimales ?**
    - a) `num.toFixed(2)` ✓
    - b) `num.toPrecision(2)`
    - c) `num.decimal(2)`
    - d) `format(num, 2)`

Note: Les réponses correctes sont marquées avec ✓
