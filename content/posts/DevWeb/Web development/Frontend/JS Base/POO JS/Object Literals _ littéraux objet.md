# Object Literals / littéraux objet

Exemple:
book1 est un littéral d'objet:
````js
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
````



