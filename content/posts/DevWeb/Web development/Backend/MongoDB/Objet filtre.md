# Objet filtre 

Toute combinaison des éléments suivants peut être utilisée à l'intérieur d'un objet filtre pour effectuer des requêtes complexes.

- $or
- $and
---

- $gt: supérieur à 
- $gte: supérieur ou égal à
Exemple:
````
db.users.find({ age: { $gt: 12 } })
db.users.find({ age: { $gte: 15 } })
````

- $lt: moins que 
- $lte: inférieur ou égal à 
Exemple: 
````
db.users.find({ age: { $lt: 12 } })
db.users.find({ age: { $lte: 15 } })
````
----
- $set: remplace la valeur d'un champ par la valeur spécifiée.
- $push: ajoute une nouvelle valeur dans un tableau.
- $in: sélectionner les documents dans lesquels la valeur d'un champ est égale à n'importe quelle valeur du tableau spécifiée.
- $elemMatch: limite le contenu d'un array.