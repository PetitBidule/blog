# POO JS 

La POO pour Programmation Orientée Objet consiste à encapsuler les données et les traitements en relation avec ces données dans des objets. 

## Les bases de l'objet

Un objet est une collection de données  et/ou de fonctionnalités, qui souvent se composent de plusieurs variables et fonctions, appelées propriétés et méthodes quand elles sont  dans des objets.

Exemple: 
````javascript
var personne = {};
````


````javascript
var personne = {
  nom: ["Jean", "Martin"],
  age: 32,
  sexe: "masculin",
  interets: ["musique", "skier"],
  bio: function () {
    alert(
      this.nom[0] +
        " " +
        this.nom[1] +
        " a " +
        this.age +
        " ans. Il aime " +
        this.interets[0] +
        " et " +
        this.interets[1] +
        ".",
    );
  },
  salutation: function () {
    alert("Bonjour ! Je suis " + this.nom[0] + ".");
  },
};
````

Pour un cours video sur la POO en JS:


https://www.youtube.com/watch?v=vDJpGenyHaA&list=PLillGF-RfqbbnEGy3ROiLWk7JMCuSyQtX&index=12