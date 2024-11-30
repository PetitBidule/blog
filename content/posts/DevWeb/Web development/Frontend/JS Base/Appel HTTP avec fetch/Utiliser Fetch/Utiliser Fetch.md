# Utiliser Fetch

L'API Fetch fournit une interface JS pour l'accès et la manipulation des parties de la pipeline HTTP

## Créer une requête fetch

Une requête fetch basique est vraiment simple à initier.

````js
const myImage = document.querySelector('img');

fetch('flowers.jpg')//nom de l'image
	.then(function(response){
		return response.blob();
})