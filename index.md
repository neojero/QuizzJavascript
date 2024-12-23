---
marp: true
theme: default
markdown.marp.enableHtml: true
paginate: true
---
<style>

section {
  background-color: #fefefe;
  color: #333;
}

img[alt~="center"] {
  display: block;
  margin: 0 auto;
}

blockquote {
  background:rgb(230, 227, 222);
  border-left: 10px solidrgb(203, 15, 52);
  margin: 1.5em 10px;
  padding: 0.5em 10px;
}
blockquote:before{
  content: unset;
}
blockquote:after{
  content: unset;
}
</style>

# ![center](./asset/logo.jpg)

---

> [Notes]
> liste des thèmes du questionnaire :

    - Syntaxe et Types de Données
    - Fonctions
    - Objets et Prototypes
    - Manipulation du DOM
    - Événements
    - Asynchrone (Promesses, Async/Await)
    - Modules et Import/Export
    - Gestion des Erreurs

> [!IMPORTANT]
> plusieurs réponses sont possible sur certaines questions
---
<!-- _class: lead -->
**Question 1** : *Comment écrire "Hello" dans une boîte d'alerte?* 
- [ ] ```alertBox("Hello");```
- [ ] ```alert("Hello");```
- [ ] ```msg("Hello");```
- [ ] ```msgBox("Hello");```

**Question 2** : *Quelle est la bonne manière d'écrire un commentaire en JavaScript?* 
- [ ] ``` <!-- ... --> ```
- [ ] ``` // ... ```
- [ ] ``` \\ ... ```
- [ ] ``` {# ... #} ```
  
---
<!-- _class: invert -->

**Question 3** : *Comment pouvez-vous détecter le nom de l'application du navigateur du client?*  
- [ ] ``` navigator.appName; ```
- [ ] ```navigator.browserName``` 
- [ ] ```browser.name``` 

**Question 4** : *Comment déclarez-vous une nouvelle date en JavaScript?* 
- [ ] ``` var date = Date(); ```
- [ ] ``` var date = date(now); ```
- [ ] ``` var date = new Date(); ```
- [ ] ``` var date = date().current(); ```

---

**Question 5** : *Lequel est correct?*
- [ ] ``` i =+ 1; ```
- [ ] ``` i += 1; ```
- [ ] ``` i = i++1; ```
- [ ] ``` +i+; ```

**Question 6** : *Quelle fonction est utilisée pour charger l'URL suivante dans la liste de l'historique?*
- [ ] ``` window.history.next(); ```
- [ ] ``` window.history.load_next(); ```
- [ ] ``` window.history.forward(); ```
- [ ] ``` window.history.load_forward(); ```

---

**Question 7** : *Comment écrivez-vous n'importe quoi dans la page Web en JavaScript?  
- [ ] ``` window.write(...) ```
- [ ] ``` document.write(...) ```
- [ ] ``` window.page.write(...) ```
- [ ] ``` document.page.write(...) ```

**Question 8** : *Comment créez-vous un tableau JavaScript?*
- [ ] ``` var fruits = "banana", "apple", "peach"; ```
- [ ] ``` var fruits = (1:"banana", 2:"apple", 3:"peach"); ```
- [ ] ``` var fruits = ["banana", "apple", "peach"]; ```
- [ ] ``` var fruits = 1 = ("banana"), 2 = ("apple"), 3 = ("peach"); ```

---

**Question 9** : *Peut-on définir n'importe quel style à une balise HTML en utilisant JavaScript?* 
- [ ] ``` oui ```
- [ ] ``` non ```

**Question 10** : *Que va renvoyer le code suivant ?*
```js
let arr = [1,2,3,4,5];
arr.slice(0,3);
```
- [ ] ``` Renvoie [4,5] ```
- [ ] ``` Renvoie [1,2,3,4] ```
- [ ] ``` Renvoie [1,2,3] ```
- [ ] ``` Renvoie [1,2,3,4,5] ```

---

**Question 11** : *Lequel des suivants est utilisé pour identifier un tableau?* 
- [ ] ``` === ```
- [ ] ``` typeof ```
- [ ] ``` isarrayType() ```
- [ ] ``` == ```

**Question 12** : *Comment appelle-t-on les fonctions sans valeur de retour?* 
- [ ] ``` Fonction statique ```
- [ ] ``` Méthode ```
- [ ] ``` Procédure ```
- [ ] ``` Fonction dynamique ```

---

**Question 13** : *JavaScript n'est pas un langage sensible à la casse.*
- [ ] ``` vrai ```
- [ ] ``` faux ```

**Question 14** : *Quelle méthode convertit une chaîne JSON en un objet JavaScript?*

- [ ] ``` JSON.parse()```
- [ ] ``` JSON.stringify()```
- [ ] ``` Object.parse()```
- [ ] ``` String.parseJSON()```
- [ ] ``` JSON.toObject()```

---

**Question 15** : *Comment créez-vous une promesse en JavaScript?*
- [ ] ``` new Promise()```
- [ ] ``` Promise.create()```
- [ ] ``` createPromise()```
- [ ] ``` Promise()```

**Question 16** : *Quelle méthode est utilisée pour sérialiser un objet en chaîne JSON en JavaScript?*

- [ ] ``` JSON.stringify()```
- [ ] ``` JSON.parse()```
- [ ] ``` Object.toString()```
- [ ] ``` Stringify.object()```

---

**Question 17** : *Comment déclarez-vous une classe nommée 'Car' en JavaScript?*

- [ ] ``` class Car {}```
- [ ] ``` function Car() {}```
- [ ] ``` new Class(Car)```
- [ ] ``` createClass('Car')```

**Question 18** : *Comment définissez-vous une fonction asynchrone en JavaScript?*

- [ ] ``` function async() {}```
- [ ] ``` async function() {}```
- [ ] ``` function() async {}```
- [ ] ``` async() function {}```

---

**Question 19** : *Comment pouvez-vous empêcher une action par défaut dans un gestionnaire d'événements en JavaScript?*

- [ ] ``` event.preventDefault()```
- [ ] ``` event.stop()```
- [ ] ``` preventDefault()```
- [ ] ``` event.stopPropagation()```

---

**Question 20** : *Que fait la méthode 'map' en JavaScript?*

- [ ] ``` Associe une valeur à une clé dans un objet```
- [ ] ``` Crée un nouveau tableau avec les résultats de l'appel d'une fonction pour chaque élément du tableau```
- [ ] ``` Applique une fonction contre un accumulateur et chaque élément dans le tableau (de gauche à droite)```
- [ ] ``` Recherche des éléments dans un tableau qui correspondent à une condition```

---

**Question 21** : *Quelle méthode JavaScript est utilisée pour trier les éléments d'un tableau?*

- [ ] ``` array.sort()```
- [ ] ``` sort(array)```
- [ ] ``` array.order()```
- [ ] ``` order(array)```

**Question 22** : *Comment pouvez-vous convertir la chaîne '3.14' en un nombre en JavaScript?*

- [ ] ``` Number('3.14')```
- [ ] ``` parseNum('3.14')```
- [ ] ``` int('3.14')```
- [ ] ``` parseFloat('3.14')```

---

**Question 23** : *Dans quel élément mettez-vous JavaScript?*

- [ ] ``` <var>```
- [ ] ``` <script>```
- [ ] ``` <section>```
- [ ] ``` <code>```

---

**Question 24** : *Quel est le résultat de la variable "docs"?*
```js
var docs;
if (10 > 4) {
  docs = true;
} else {
  docs = 55;
}
```
- [ ] ``` true```
- [ ] ``` 55```
- [ ] ``` undefined```

---

**Question 25** : *Comment arrondissez-vous le nombre 5.35 au plus proche entier?*

- [ ] ``` rnd(5.35)```
- [ ] ``` Math.rnd(5.35)```
- [ ] ``` round(5.35)```
- [ ] ``` Math.round(5.35)```

**Question 26** : *Lequel est la syntaxe correcte pour ouvrir une nouvelle fenêtre appelée "docs"?*

- [ ] ``` docs = window.open.new("http://www.docs.com");```
- [ ] ``` docs = window.new("http://www.docs.com");```
- [ ] ``` docs = window.open("http://www.docs.com");```
- [ ] ``` docs = window("http://www.docs.com");```

---

**Question 27** : *Quel sera le résultat du code suivant?*
```js
let stringToNum = parseInt("123ab");
```
- [ ] ``` 123```
- [ ] ``` Exception```
- [ ] ``` 123ab```
- [ ] ``` NaN```

**Question 28** : *Quel sera le résultat de l'instruction suivante?*
```js
let total = eval("10*10+8");
```
- [ ] ``` 10*10+8```
- [ ] ``` 108 en tant que valeur entière```
- [ ] ``` 108 en tant que chaîne```
- [ ] ``` Exception levée```

---

**Question 29** : *Que se passe-t-il si l'instruction 'return' n'a pas d'expression associée?*

- [ ] ``` Elle va déclencher une exception```
- [ ] ``` Elle va retourner 0```
- [ ] ``` Elle va retourner undefined```
- [ ] ``` Aucune des options mentionnées```

**Question 30** : *À quoi se réfère 'this' dans une méthode JavaScript?*

- [ ] ``` L'objet global```
- [ ] ``` La fonction elle-même```
- [ ] ``` L'objet qui a appelé la méthode```
- [ ] ``` L'objet document```

---

**Question 31** : *Quelle méthode est utilisée pour arrondir un nombre au plus proche entier en JavaScript?*

- [ ] ``` Math.round()```
- [ ] ``` Math.floor()```
- [ ] ``` Math.ceil()```
- [ ] ``` Number.round()```

**Question 32** : *Quel opérateur est utilisé pour comparer à la fois la valeur et le type?*

- [ ] ```==```
- [ ] ```===```
- [ ] ```!=```
- [ ] ```!==```

---

**Question 33** : *Quelle méthode JavaScript est utilisée pour itérer sur toutes les propriétés d'un objet?*

- [ ] ``` Object.forEach()```
- [ ] ``` for...in```
- [ ] ``` Object.loop()```
- [ ] ``` forEach()```

**Question 34** : *Que fait la méthode 'splice' dans un tableau?*

- [ ] ``` Supprime et/ou ajoute de nouveaux éléments à un tableau```
- [ ] ``` Joint deux tableaux en un seul```
- [ ] ``` Trie les éléments d'un tableau```
- [ ] ``` Trouve l'indice d'un élément dans le tableau```

---

**Question 35** : *Quelle méthode JavaScript est utilisée pour retirer le dernier élément d'un tableau et renvoyer cet élément?*

- [ ] ``` pop()```
- [ ] ``` push()```
- [ ] ``` last()```
- [ ] ``` removeLast()```

**Question 36** : *À quoi sert 'break' en JavaScript?*

- [ ] ``` Pour arrêter l'exécution d'une boucle```
- [ ] ``` Pour briser le code en plusieurs lignes```
- [ ] ``` Pour sortir d'une fonction```
- [ ] ``` Pour mettre en pause le débogueur```

---

**Question 37** : *Quelle méthode est utilisée pour ajouter un ou plusieurs éléments au début d'un tableau?*

- [ ] ``` unshift()```
- [ ] ``` shift()```
- [ ] ``` push()```
- [ ] ``` prepend()```

**Question 38** : *Lequel de ces éléments n'est pas un type de données valide en JavaScript?*

- [ ] ``` Undefined```
- [ ] ``` Number```
- [ ] ``` Float```
- [ ] ``` Boolean```

---

**Question 39** : *Quelle méthode est utilisée pour transformer une chaîne en un entier en JavaScript?*

- [ ] ``` int.parse()```
- [ ] ``` Number.parseInt()```
- [ ] ``` parseInt()```
- [ ] ``` Math.parseInt()```

---

> [!WARNING]
> Un bonheur n'arrivant jamais seul... >>
> [2ème questionnaires](/second.md) 🚀

*Created with markdown & Marp by Jérôme BOEBION*  