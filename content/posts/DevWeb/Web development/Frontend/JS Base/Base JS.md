[While](#while)
[For](#for)
[For...of](#for...of)
[For...in](#for)
[L'instruction Break](#break)
# Objet 
Un objet est une structure contenant des données et des instructions en rapport avec ces données 
Il est utilisé pour stocker des ensemble de ==clés/valeurs==. 
Une paire clé-valeur 
# Primitive 
- String
- Number
- Boolean
- Null
- Symbol
- Undefined
- Bigint (equivalent a double en dart)
# Les variables

Les variables sont des conteneurs dans lesquels on peut stocker des valeurs. Pour commencer, il faut déclarer une variable avec le mot-clé **let**, **const** ou **var**, cependant on utilise plus var car trop ancien, on utilisera donc soit let si la valeur va changer, sinon const si la valeurs ne change pas.

| Variables | Explication | Exemple |
| --- | --- | --- |
| Chaine de caractère (**String**) | Une suite de caractère connue sous le nom de chaîne. | let myVariable= 'Bob' |
| Nombre (Number) | Un nombre. | let myVariable = 10; |
| Boléen | Une valeur qui signifie **vrai** ou **faux**. | let myVariable = true |
| Objet | Tout est un objet en JS et peut-être stocké dans une variable. | let myVariable = {objet: cookie} |
| Tableau | Une structure qui permet de stocker pls valeurs valeurs dans une seule variable | let myVariable = \[1, 'bob', 5775\]; |

# **Les conditions**

VRAI ET VRAI = VRAI
VRAI ET FAUX = FAUX
FAXU ET FAUX = FAUX

VRAI OU VRAI = VRAI
VRAI OU FAUX = VRAI
FAUX OU FAUX = FAUX

Exemple:

```Javascript
const age = 17
const pays = 'US'
const peutConduireFrance = pays == 'FR' && age >= 18
const peutConduireUS = pays === 'US' && age >= 16

if (peutConduireFrance || peutConduireUS){
    console.log('Vous avez le droit de conduire ')
}else{
    console.log("Vous n'avez pas le droit de conduire")
}
```

L'inverse

!true va donner false
false va donner true
!"" va donner true
!!"" va donner false

```Javascript
if (!peutConduireFrance && !peutConduireUS){
   console.log("Vous n'avez pas le droit de conduire ")
}
```

# while

L'instruction ***while*** permet de créer une boucle qui s'exécute tant qu'une condition de test est vérifiée. La condition est évaluée avant d'exécuter l'instruction contenue dans la boucle.

### **Structure While: quand on ne connait pas précisément le nombre d'itérations à exécuter.**

Exemple

```js
let n = 0

while (n<3){
    n++
}
console.log(n)
// on obtient: 
// 3
```

## Syntaxe

> **while (condition){
> instruction
> }**

## Paramètres

### condition

Une expression qui est évaluée avant chaque passage dans la boucle. Si cette expression est évaluée à vrai, instruction est éxecutée. Lorsque la condition n'est pas vérifiée, l'exécution se poursuit avec l'instruction qui suit la boucle while.

### instruction

Une instruction optionnelle qui doit etre exécutée tant que la condition d'entrée est vérifiée. Afin d'exécuter plusieurs instructions au sein de la boucle, on utilisera un bloc d'instructions ({...}) poour les regrouper.

Exemple

```js
let n = 0
let x = 0

while( n < 3 ){
    n++;
    x += n
}
```

A chaque itération, la boucle incrémente la valeur n et l'ajoute à x.
Ainsi, x et n prennent les valeurs suivantes:

- Après la première itération: n = 1 et x = 1
- Après la deuxième itérations: n = 2 et x = 3
- Après la troisième itération: n = 3 et x = 6

Une fois que la troisième itération est exécutée, la condition n < 3 n'est plus vérifiée et donc ma boucle se termine.

# Break

L'instruction ***break*** est utilisée pour finir l'exécution d'une boucle, d'une instruction switch, ou avec un label.

- Lorsque break est utilisée sans label sans label, il provoque la fin de l'instruction *while*, *for*, ou *switch* dans laquelle il est inscrit (on finit l'instruction la plus imbriquée), le controle est ensuite passé à l'instruction suivante.
- Lorsque break est utilisé avec un label, il provoque la fin de l'instruction correspondante.

## Syntaxe

> **1\. break;
> 2\. break label;**

Exemple 1:

```js
for (i = 1; i <= 10; i++){
    if( i === 5 ) break;
    console.log(i)
}
// lorsque i = 5 on va sortir du for 
// 	donc obtient 1, 2, 3, 4
// (le break permet de d'arreter la boucle 
// dans notre cas lorsque i aura atteint 5)
```

# **For**

l'instruction ***for*** crée une boucle composée de 3 expressions optionnelles séparées par des points-virgules et encadrées entre des parenthèses qui sont suivies par une insttruction

### **Structure For: quand on connait d'avance le nombre d'itérations à exécuter.**

Exemple:

```js
let str = ""

for (let i = 0; i < 9; i++){
    str = str + i;
}
console.log(str)
// on trouve "012345678"
```

## syntaxe

> for(\[initialisation\]); \[condition\]; \[expression-finale\]
> instruction

## Paramètres:

### **initialisation**:

Une expression ou une déclaration de varaible. Cette expression est évaluée une fois avant que la boucle démarre.

### **condition**

Une expression qui est évaluée avant chaque itération de la boucle. Si cette expression est vérifiée, l'instruction est éxécutée.

### **expression finale**

Une expression qui est évaluée à la fin de chaque itération

### **Instruction**

Une instruction qui est exécutée tant que la condition de la boucle est vérifiée. Afin d'éxécuter plusieurs instructions au sein d'une telle boucle, il faudra utiliser une instruction de bloc.

# for...in

L'instruction ***for...in*** permet d'itérer sur les propriétés énumérables d'un objet qui ne sont pas des symboles. Pour chaque propriété obtenue, on exécute une instrcution.

Exemple

```js
const object = {a:1, b:2, c:3};

for(const property in object){
    console.log(`${property}: ${object[property]}`);
}
// on obtient: 
// "a: 1"
// "b: 2"
// "c: 3"

```

## Syntaxe

> for (variable in objet){
> instructions
> }

## Paramètres:

### **variable**

Un nom de propriété différent est assigné à la variable à chaque itération de la boucle.

### **objet**

L'objet dont les propriété énumérables et qui ne sont pas des symboles sont parcourues par la boucles.

# For...of

L'instruction for..of permet de créer une boucle *Array*
(=L'objet global Array est utilisé pour créer des tableaux. Les tableaux sont des objets de haut-niveau semblables à des listes.)
qui parcourt un objet itérable et qui permet d'éxecuter une ou plusieurs instructions pour la valeur de chaque propriété.

Exemple

```js
const array1 = ["a","b","c"];

for (const element of array1){
    console.log(element);
}
// on obtient:
// "a"
// "b"
// "c"
```

# Fonctions

Toute fonctions JS est en fait un objet *Function*

Le mot clé <u>this</u> ne fait pas référence à la fonction en cours d'éxécution. Il faut donc faire référence aux objets Function par leurs noms, et ce meme au sein du corps de la fonction

## Définir une fonction

> function nom (\[param \[ , param \[ , ... param \] \] \] ){
> instructions
> }

**nom** = le nom de la fonction

**param** = le nom d'un argument à passer à la fonction (une fonction pouvant avoir jusqu'a 255 arguments).

**instructions** = les instructions qui forment le corps de la fonction.

## return

L'instruction *return* met fin à l'éxécution d'une *fonction* et définit une valeur à renvoyer à la fonction appelante.

Exemple

```js
function getReactArea(width, height){
    if(width > 0 && height > 0 )
        return width * height;
    return 0;
}
console.log(getReactArea(3,4))
// cela nous donnera 12
console.log(getReactAera(-3,4))
// cela nous donnera 0
```

### Syntaxe

> return \[expression\];

expression = l'expression dont on souhaite renvoyer la valeur. Si elle est absente, la valeur renvoyée par défaut sera <u>undefined</u>

## Bonus: fonction impure vs fonction pure

fonction pure: renvoie toujours la même sortie / ne produit aucun effet secondaire.
Conclusion:
Une fonction n'est pure que si, étant donné la même entrée, elle produira toujours la même sortie. 



# Classes

Les classes sont juste des fonctions spéciales. Ainsi, les classes sont définies de la meme façon que les fonctions: par des déclaration, ou pas des expression.

## Les déclarations de classes

Pour utiliser une déclaration de classe simple, on utilise le mot clé class, suivi par le nom de la classe que l'on déclare dans notre exemple rectangle.

Exemple:

```js
class Rectangle{
    constructor(hauteur, largeur){
        this.hauteur = hauteur;
        this.largeur = largeur;
    }
}
```

## constructor

La méthode constructor est une méthode qui est utilisée pour créer et initialiser un objet lorsqu'on utilise le mot clé ***class***

Exemple:

```js
class Polygon{
    constructor(){
        this.name = 'Polygon';
    }
}
const poly1 = new Polygon();
console.log(poly1.name);
// Cela nous donnera 'Polygon'
```

### Syntaxe

> constructor(){...}
> constructor(){argument0}
> constructor(){argument0, argument1, ...}

## L'opérateur new

L'opérateur new permet de créer une instance d'un certain type d'objet à partir du constructeur qui existe pour celui-ci.

Le mot clé new, utilisé avec une fonction, applique les 4 étapes suivantes:

1.  Il crée un nouvel objet à partir de zéro
2.  Il lie cet objet à un autre objet en le définissant comme son prototype.
3.  Le nouvel objet, créé à l"étape 1, est passé comme valeur **this** à la fonction
4.  Si la fonction ne renvoie pas d'objet, c'est la valeur this qui est renvoyée.

Exemple:

```js
function Car(make, model, year){
    this.make = make;
    this.model = model;
    this.year = year;
}
consr car1 = new Car('Eagle', 'Talon TSi', 1993);
```

### Syntaxe

> new constructeur\[(\[arguments\])\]

## Extends

Le mot-clé extends est utilisé dans les déclarations et expressions de classes afin de signifier qu'un type représenté par une classe hérite d'un autre type.

Exemple:

```js
class personne{
    constructor(firsname, lastname){
        this.firstname = firstname;
        this.lastname = lastname;
    }
}
class Users extends personne{
    constructor(firstname, lastname){
        super(firstname, lastname)
    }
}
let users = new Users('John', 'Doe')
```

Extends permet de reprendre la partie déjà faite dans notre cas personnes pour y ajouter une nouvelle class Users, cependant cette class aura les propriété de la class personne.

## L'opérateur this

En JavaScript, le mot clé ***this*** se comporte légèrement différemment des autres langages de programmation. Son comportement variera également légèrement selon qu'on utilise le mode strict ou le mode non-strict.

Exemple:

```js
let user = {
    prenom : "John"
    sayHi(){
        console.log('Hello ${this.prenom}');
    }
}
user.sayHi()
// cela nous renverra 'Hello John'
```

# Throw et try...catch

L'instruction throw pemet de lever une exception définie par l'utilisateur. L'exécution de la fonction courante sera stoppée (les instructions situées après l'instruction throw ne seront pas exécutées) et le controle sera passé au premier bloc catch de la pile d'appels. Si aucun bloc catch ne se trouve dans les fonctions de la pile d'appels, le programme sera terminé.

Exemple

```js
function getRectArea(width, height){
    if(isNaN(width) || isNaN(height)){
        throw 'Parameter is not number!';
    }
}
try {
    getRectArea(3, 'A');
}catch(e){
    console.error(e)
}
// cela nous renvoie 'Parameter is not a number'
```

## Syntaxe

> throw expression ;

L'instruction **try...catch** regroupe des instructions à exécuter et définit une réponse si l'une de ces instructions provoque une exception.

Exemple:

```js
try{
    nonExistentFunction();
}catch(error){
    console.error(error)
}
// cela nous renvoie "ReferenceError: nonExistentFunction is not defined"
```

## Syntaxe

> try {
> tryStatements
> } catch (exeptionVar) {
> catchStatements
> }finally {
> finallyStatements
> }

##### tryStaments:

Les instructions à exécuter

##### catchStatements:

Instruction exécutée si une exception est levée dans le *try-block* (parite au dessus)

##### exceptionVar (Optionnel)

##### finallyStatements:

Instructions exécutées avant que le flux de controle ne quitte la *try...catch...finally* construction.