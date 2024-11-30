# Read

- ==db.collection.find()==: 

**Utilité**: Obtiens tous les documents trouver.


- ==db.collection.find(*objet filtre*, *projection*)==:

**Utilité**: Sélectionne les documents dans une collection et renvoie les résultats.
**Paramètre**: objet filtre qui spécifie les critères de sélection, projection
Retourne:  renvoie tous les documents en rapport avec l'objet filtre.                       

Exemple:
````
db.users.find({ name: “Kyle” })
//renvoie tous les documents de la collection "users" 
//avec comme "name" kyle
````

### Projection : 

Le projection est un processus de sélection des domaines que nous voulons retourner dans notre résultat.
Peut etre utilsée comme second paramèter pour la méthode find.
Pour exclure l'élément de la zone, on doit mettre 0 sinon 1 pour focus sur l'élément 
````
db.collection.find( <query>, <projection> )
db.collection.find( <query>, { <field> : 1 }) // pour exclure un champ mettre 0 

db.users.find({ name: “Kyle” }, { name: 1, age: 1 })
//renvoie tous les documents de la collection users, dont "name" 
//correspond à "kyle", les seuls champs que nous obtiendront seront 
le "name" et "age".
````


- ==db.collection.findOne()==:
**Utilité**: Renvoie le premier document qui correspond à l'objet filtre. 
Paramètre: un objet filtre qui spécifie les critères de sélection

Exemple:
````
db.users.findOne({ name: “Kyle” })
// renvoie le premier document de la collection "users", dont name correspnd à "kyl".
````