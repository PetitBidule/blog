# Classe

Les classes ont été introduites avec ECMAScipt 2015. Elle fournit uniquement une syntaxe plus simple pour créer des objets et manipuler l'héritage.

Les classes sont juste des fonctions spéciales. Elles sont donc définies de la meme façon que les fonctions. 

## Déclaration d'une classe

Pour déclarer une classe, on utilisera le mot-clé "class", suivi par le nom de la classe que l'on délcare. (généralement la 1 lettre du nom de la classe est en majuscule).

````javascript
class Book{
	constructeur(title, author, year){ // on retrouve ici notre constructeur.
		this.title = title;
		this.author = author;
		this.year = year;
	}
	
	getSummary(){ // notre fonction
		return `${this.title} was written by ${this.author}`
	}
	getAge(){// ici nous créons une fonction "getAge" qui va nous renvoyer depuis combien d'années le livre est sorti.
		const year = new Date() - getFullYear()-this.year;
		return `${this.title} is ${year} years old`
	}
}

// Créons / Instancier un objet
const book1 = new Book('Book One', "John Doe", "2020");