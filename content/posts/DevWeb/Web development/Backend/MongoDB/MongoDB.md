# MongoDB 



- ### Database:
Un conteneur pour les collections*. C'est la meme chose qu'une base de donnée en SQL.
Dans la plupart du temps, chaque projet aura sa propre base de donnée remplis de différentes collections. 

- ### Collection:
Une Collection est un groupement de document à l'intérieur d'une base de données. 

- ### Document:
Un enregistrement à l'intérieur d'une collection. Il y aura un document par objet dans la collection. Un document est également un objet JSON.

- ### Field:
Une paire clé-valeur dans un document. Chaque document comporte un certain nombre de champs qui contiennent des infromations.
Comme par exemple, le nom, l'adresse, les loisirs etc...

## Commands de base:
 
- ==show dbs==: Montre l'ensemble des base de donneés,
- ==use "dbname"==: change la base de donnée par celle sélectionné 
- ==db==: affiche le nom de la base de donnée actuelle,
- ==show collections==: affiche toutes les collections de la base de donnée actuelle
- db.dropDatabase(): supprime la base de donnée actuelle,



## opérateur 


.limit(): limite les résultats de la requte dans un ordre spécifée 
.sort(): utilisé pour renvoyer les résultats de la requete, entre () utiliser 1 pour l'ordre croissant, et -1 pour l'ordre décroissant. 


### Pipeline Aggregation

- $project: signifie les champs de documents de sortie, 1 inclus, 0 exclus.
- $set: crée de nouveaux champ oiu moodifie la valeur des champs existants.
- $count: crée un nouveau documents, avec le nbr de documents à cette étape.
- $limit
- $out: crée une nouvelle collection avec les résultat dedans
- $sort
- $match
- $group



db.collection.findAndModify()
db.collection.replaceOne()



db.collection.countDocuments():
permet de compter le nombre de documents qui correspondent à une requete 
````
db.collection.countDocuments( <query>, <options> )
````



.db.collection.aggregate()