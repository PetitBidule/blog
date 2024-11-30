
SSRF signifie Server-Side Request Forgery (falsification de requête côté serveur). 
Il s'agit d'une vulnérabilité qui permet à un utilisateur malveillant de forcer le serveur web à effectuer une requête HTTP supplémentaire ou modifiée sur la ressource choisie par l'attaquant. 

## Exemple

Les vulnérabilités SSRF peuvent être repérées dans les applications Web de différentes manières. 

- Lorsqu'une URL complète est utilisée dans un paramètre de la barre d'adresse:![[Pasted image 20240926143538.png]]
- Un champ caché dans un formulaire:![[Pasted image 20240926180055.png]]
- Une URL partielle telle que simplement le nom d'hôte:![[Pasted image 20240926180127.png]]
- Le chemin de l'URL:![[Pasted image 20240926180212.png]]

## Le counter:

### Liste de refus:

Une Liste de refus est une liste dans laquelle toutes les demandes sont acceptées, à l'exception des ressources spécifiées dans une liste ou correspondant à un modèle particulier.

### Liste d'autorisation:

Une liste d'autorisation est une liste dans laquelle toutes les demandes sont refusées, sauf si elles apparaissent sur une liste ou correspondent à un modèle particulier, comme une règle selon laquelle une URL utilisée dans un paramètre doit commencer par https://theolegoat.com (par exemple xD);

### Ouvrir la redirection

Une redirection ouverte est un point de terminaison sur le serveur où le visiteur du site-web est automatiquement redirigé vers une autre adresse de site web. 