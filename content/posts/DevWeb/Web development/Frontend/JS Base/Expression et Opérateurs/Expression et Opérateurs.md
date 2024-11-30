# Expression et Opérateurs

# L'opérateur conditionnel 

**L'opérateur (ternaire) conditionnel** est le seul opérateur JavaScript qui comporte 3 opérandes. Cet opérateur est fréquemment utilisé comme raccourci pour la déclaration d'instruction *if/else*.
(le ternaire permet de simplifier une condition)

Exemple:
```js
function getFree(isMember){
	return (isMember ? '$2.00' : '$10.00');
}
console.log(getFee(true));
// expected output: "$2.00"

console.log(getFee(false));
// expected output: "$10.00"

console.log(getFee(null));
// expected output: "$10.00"
```

## Syntaxe: 
	
> condition ? expressionSiVrai : expressionSiFaux

##### Condition 
Une expression qui est évaluée en un booléen (*true* ou *false*)

##### expressionSiVrai
Une expression qui est si la condition est équivalente à *true* 

##### expressionSiFaux
Une expression qui est évaluée si la condition est équivalente à *false* 

# Spread Syntax (...)

La syntaxe **spread(...)** permet à un itérable, tel qu'un *tableau* ou *une chaine* d'etre étendu aux endroits où zéro ou plusieurs arguments (pour les appels de fonction) ou éléments (pour les littéraux de tableau) sont attendus.

Exemple:
````js
function sum(x, y, z){
	return x + y + z;
}
const numbers = [1, 2, 3]

console.log(sum(...numbers));//on obtient 6
console.log(sum(2, ...numbers));// on obtient 5
````

**Quand l'utilisé ?:**
La syntaxe de propagation peut etre utilisée lorsque tous les éléments d'un objet ou d'un tableau doivent etre inclus dans un nouveau tableau ou objetn ou doivent etre appliqués un par un dans la liste des arguments d'un appel de fonction.