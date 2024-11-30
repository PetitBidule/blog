# Update

- ==db.collection.updateOne()==:
**Utilité**: Metter à jour le premier document au sein de la collection qui correspond au filtre
**Paramètre**:
- filtre: les critères de solution pour la mise à jour 
- update: les modifications à appliquer
- upsert: falcultatif

````
db.users.updateOne({ age: 20 }, { $set: { age: 21 } })
//fais passer le 1 document dont l'age = 20 à 21
````

- ==db.collection.updateMany()==:
**Utilité**: Metter à jour tous les documenst au sein de la collection en fonction du filtre
Paramètre:
- les meme  que le updateOne()

````
db.users.updateMany({ age: 12 }, { $inc: { age: 3 } })
// fais tous les documents dont l'age = 12 en ajoutant 3.
````
