# Delete

- ==db.collection.deleteOne()==:

**Utilité**: supprime le premier document qui correspond au filtre
**paramètre**: filtre

Exemple:
````
db.users.deleteOne({ age: 20 })
// supprime le premier document de la collection "users" qui correspond à age: 20
````

- ==db.collection.deleteMany()==:

**Utilité**: supprime tous les documents de la collection qui correspond au filtre
**paramète**: filtre

Exemple:
````
db.users.deleteMany({ age: 12 })
//supprime tous les documents de la collection "users" qui contient age : 12
````