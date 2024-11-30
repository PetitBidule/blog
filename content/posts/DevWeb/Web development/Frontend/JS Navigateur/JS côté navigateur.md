# Document:

L'interface Document représente n'importe quelle page web chargée dans le navigateur et sert de point d'entrée pour accéder au contenu de la page sui est formé par ==l'arbre du DOM==

- L'arbre du DOM = Un document HTML n'est au final qu'un arbre d'éléments HTML et de noeuds textes qu'il est possible de parcourir de différentes manières. Cet arbre est appellé le DOM.
    ![arbre du DOM.jpg](../../../_resources/arbre%20du%20DOM.jpg)
    Quand on récupère un élément dans la page on récupère en fait un nœud dans le DOM. Il est possible de naviguer dans l'arbre à partir d'un élément préalablement récupéré.

* * *

# Element:

Element est la classe de base la plus générique dont héritent tous les objets qui représentent des éléments d'un Document.

# Node:

Tout dans un document est un noeud
(...voir plus)

## Relation de noeud

Les noeuds de l'arborescence des noeuds ont une relation hiérarchique les uns avec les autres.
Les termes parent, enfant et frère sont utilisés pour décrire les relations.
- Dans une arborescence de noeuds, le noeud est appelé la racine
- Chaque noeud a exactement un parent, sauf la racine
- Un noeud peut avoir plusieurs fils
- Les frères et soeurs sont des noeuds avec le même parent.

Exemple; Prenons le code suivant:
````html
<html>
	<head>
		<title>DOM Tutoriel</title>
	</head>
	<body>
		<h1>Leçon Noeud</h1>
		<p>Hello World!</p>
	</body>
</html>
````
À partir du code HTML, on peut voir que:
- html est le noeud racine et il n'a pas de parents;
- html est le parent de head et body;
- head est le premier enfant de html ;
- body est le dernier enfant de html;

- head a un enfant title;
- title a un enfant (un noeud de texte):"DOM Tutoriel";
- body a 2 enfants: h1 et p;
- h1 a un enfant: "Leçon Noeud";
- p a un enfant: 'Hello World!';
- h1 et p sont frères et soeurs;

# NodeList:
Les objets NodeList sont des collections de noeuds comme celles retournées par Node.childNdes.
La NodeList n'est pas un tableau (array), il est possible d'itérer dessus en utilisant forEach(). Il peut également être converti en tableau (array) en utilisant Array.from().
## document.querySelector

La méthode **querySelector()** de l'interface Document retourne le premier Elément dans le document correspondant au sélecteur - ou groupe de sélecteurs - spécifiés.

### Syntaxe

> element = document.querySelector(sélecteurs);

Exemple:

```html
<div id='text'>Hello World</div>
```

```js
const element = document.querySelector('#text')
```

## document.querySelectorAll()	

La méthode **querySelectorAll()** de l'element renvoie une NodeList statique représentant une liste des éléments du document qui correspondent au groupe de sélecteurs spécifiés.
````js
const matches = document.querySelectorAll('p');

const matches2 = documentSelectorAll("div.notes, div.alert")
// Cet exemple renvoie la liste de tous les éléments div du document dont l'attribut de classe a pour valeur 'note' ou 'alert':
````

## element.innerHTML:

La propriété **Element.innerHTML** de Element récupère ou définit la syntaxe HTML décrivant les descandants de l'élément.
Souvent utiliser pour récupérer ou écrire du texte dans un élément.
(Renvoie le contenu HTML de l'élément)
Exemple:
````js
element.innerHTML = '<p>Bonjour</p>'
````

## Node.innerText:

Node.innerText est une propriété représentant le contenu textuel "visuellement rendu" d'un noeud.
Exemple:
````js
element.innerText = 'Bonjour'
````

## Element.style:

Permet de récupérer les styles associés à l'élément.
> element.style.backgroundColor = "red". 

CSSStyleDeclaration
Objet contenant toutes les propriétes css possibles
## Element.classList:

Permet de récupérer les styles associés à l'élément.
> element.classList.add( 'red' )
Ajoute une class à l'élément

### Méthodes:
==add==: 
Ajoute les classes spécifiées. Si une classe est déjà assignée en attribut des cet élément, elle est ignorée.
==remove==:
Supprime les classes spécifiées
==replace==:
Remplace une classe par une autre.
## Element.setAttribute()

Ajoute un nouvel attribut ou change la valeur d'un attribut existant pour l'élément spécifié. Si l'attribut existe déjà, la valeur est mise à jour; sinon, un nouvel attribut est ajouté avec le nom et la valeur spécifiés.

### Syntaxe:
> Element.setAttribute(name, value);

==name==:
Une chaîne de caractère spécifiant le nom de l'attribut pour lequel la valeur doit être définie. 
==value==:
Une chaîne de caractère contenant la valeur à affecter à l'attribut. Toure valeur spécifiée qui n'est pas une chaîne de caractère, est convertie automatiquement en chaîne.













