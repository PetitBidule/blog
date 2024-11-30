# Sucre syntaxique 

En javascript il existe pas mal de syntaxes alternatives qui va nous permettre d'écrire du code plus simplement. Cette simplification est appelée "sucre syntaxique"
Nous allons retrouver par exemple:
### l'incrementation
### les conditions: ternaire, opérateurs booléens, 
Bonus: 
````javascript
const b = a || 3 // ne vaudra 3 que si la valeur de a est false
const c = a && 3 // ne vaudra 3 que si la valeur de a est true
````
(Opérateur de coalescence des nuls (Nullish coalescing operator, **??**), est un opérateur logique qui renvoie son opérande de droite lorsque son opérance de gauche vaut null ou undefined)
Petit Exemple:
````javascript
const foo = null ?? 'default string';
console.log(foo);
// Expected output: "default string"

const baz = 0 ?? 42;
console.log(baz);
// Expected output: 0
````

Enfin, ?. == optional chaining et d'accéder à une propriété sur un objet s'il existe, en ronvoyant undefined si la valeur est null ou undefined

Exemple: 

````javascript
//noob
if(person && person.job && person.job.salary){
	console.log(person.job.salary.value)
}

//pro
console.log(person?.job?.salaty?.value)
````
## La déstructuration 

L'affectation par décomposition permet de créer des variables à partir des propriétés d'un objet ou des valeurs d'un tableau plus facilement.

Exemple:
```js
const [note1, note2] = [12, 16, 18, 19] //note1 = 12, note2 = 16

const person = {firstname: 'John', lastname: 'Doe'}
const {firstnamen, lastname} = person //firstname = 'John', lastname: 'Doe'
```

Cette destructuration peut etre particulièrement utile lorsqu'une fonction attend comme paramètre un objet

```js
function isMajeur ({age, country}){
		instruction
}
```

Il est aussi possible d'utiliser le **spread operator** <u>(voir expression et opérateur) </u> pour extraire tous les éléments restants dans une variable. Dans le cas des tableaux ce spread operateur doit etre utilisé pour le dernier élément seulement.

Exemple:
````js
const [note1, note2, ...rest] = [12, 16, 18, 19]//rest = [18,19]


const person = {firstname: 'John', lastname 'Doe', age: 18}

const {firstname, ...personWithoutFirstname} = person //personWithoutFirstname = {lastname: 'Doe', age: 18}
````