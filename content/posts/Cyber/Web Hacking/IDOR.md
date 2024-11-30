
Insecure Direct Object Reference est un type de vulnérabilité de contrôle d'accès
Ce type de vulnérabilité peut se produire lorsqu'un serveur Web reçoit une entrée fournie par l'utilisateur pour récupérer des objets, qu'une trop grande confiance a été accordée aux données d'entrée . 

![[Pasted image 20240926174858.png]]

IDOR fait partie de la catégorie de vulnérabilités OWSAP Broken Access Control
Cela signifie que la plupart des vulnérabilités IDOR seront trouvé après s'être authentifié auprès de l'application. 

## IDOR Conditions

- L'application révèle une référence directe à une ressource ou une opération interne
- L'utilisateur peut manipuler une URL ou un paramètre de formulaire pour modifier la référence directe
- L'application accorde l'accès à l'objet interne sans vérifier si l'utilisateur est autorisé.