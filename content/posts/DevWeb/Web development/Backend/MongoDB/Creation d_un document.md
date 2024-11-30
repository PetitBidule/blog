# Creation d'un document 

- ==db.collection.insertOne()==:

**Utilité**: Permet d'insère un seul document dans la collection spécifiée:
**Paramètre**: un document à insérer
Retourne:
- un boolean 
- un champ avec la _id valeur du document inséré 

Exemple: 
````
db.users.insertOne({ name: “Kyle” })
// on insert un document qui prend comme champ "name" 
// qui prend comme valeur "Kyle" ce champ est ainsi stocké dans 
// la collection "users"
````


- ==db.collection.insertMany()==:

**Utiliré**: Insère plusieurs documents dans la collection spécifiée:
**Paramètre**: un ensemble de documents à insérer.
Retourne:
-identique au insertOne()

Exemple
````
db.users.insertMany([{ age: 26 }, { age: 20 }])
//ici on insert 2 documents dans la collection "users".
````