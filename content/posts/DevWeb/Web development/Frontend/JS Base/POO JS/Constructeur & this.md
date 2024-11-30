# Constructeur & this

Ici présent, nous avons 2 objets, book1 et book2, ce qui est pénible car nous avonc un effet de répétition avec les fonctions "getSummary", les constructeurs existent pour éviter cela.
(ils sont utilisée pour créer et initialiser un objet).
````javascript
const book1 = { 
	//les différentes propriétés ne sont que des paires clé-valeur
	//par exemple: **title** est la clé et 'Book One' est égal à la valeur.
    title: 'Book One', 
    author: 'John Doe',
    year: '2013',
    getSummary: function(){
        return `${this.title} was written by ${this.author}`
		// ici l'opérateur this fais référence à l'objet 
    }
}
const book2 = { 
	valeur.
    title: 'Book Two', 
    author: 'theo le jeune goat',
    year: '2019',
    getSummary: function(){
        return `${this.title} was written by ${this.author}`
    }
}
````

Exemple du meme code mais avec des constructeur:

````javascript
//Constructeur:
function Book(title, author, year){// title, author et year sont des arguments 
    this.title = title;
    this.author = author;
    this.year = year;
		
		this.getSummary = function() {
			return `${this.title} was written by ${this.author}`
		};
}

//Création d'objets:
const book10 = new Book('Book One', 'Redwann', "2390")
// ici l'opérateur "new" permet de créer une instance d'un type d'objet à partir du constructeur qui existe pour celui-ci
const book11 = new Book('Book dqlmksmdqz', 'theo', "4983840")
````
