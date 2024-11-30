# Héritage

Ok, imaginons, que nous voulons créer un nouvel objet que nous allons appeller "Manga", et nous voulons que ce dernier hérite des propriété de l'objet "Book".
Dans notre cas, nous voulons que l'objet "manga" hérite de "title", "author", "year".
````javascript
//Constructeur:
function Book(title, author, year){
    this.title = title;
    this.author = author;
    this.year = year;
		
		this.getSummary = function() {
			return `${this.title} was written by ${this.author}`
		};
}

// Manga constructeur
function Manga(title, author, year, month){ // ici nous rajoutons un argument "month"
	Book.call(this, title, author, year);
	// au lieu de remarquer chaque "this", 
	//nous appellons la méthode call() qui réalise un appel 
	//à une fonction avec une valeur this donnée et des arguments.
	
	this.month = month;
}
//Création d'objets:
const manga1 = new Manga('Manga One', 'Oda', "1999", "Jan");
````

