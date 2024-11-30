# HTTP

HTTP => Hypertext Transfer Protocol
HTTP est un protocole servant à transmettre des documents hypermédias, comme HTML (mais aussi des images, des vidéos...). Il a été conçu pour la communication entre les navigateur web (coté client) et les serveurs web mais peut également être utilisé à d'autres fins.

Il suit le modèle classique client-serveur: un client ouvre une connexion, effectue une requête et attend jusqu'à recevoir une réponse.

<img src="../../../_resources/http.png" alt="http.png" width="932" height="548">

Le client communique avec le serveurs via des échanges de messages:

- les messages envoyés par le client sont appelées des requêtes
- les messages envoyés par le serveur sont appelés des réponses.

## Les messages HTTP

#### Les Requêtes:

Exemple:
![http_requetes.png](../../../_resources/http_requetes.png)

- Une **méthode** HTTP: généralement un verbe tel que GET, POST ou un nom comme OPTIONS ou HEAD qui définit l'opération que le client souhaite effectuer.
- Path (le chemin de la ressource à extraire): l'URL de la ressource à laquelle on retiré les éléments déductibles du contextes.
- La version du protocoles HTTP comme HTTP/1, HTTP/2
    (la seule différence entre les deux sera la réduction du temps de latence du HTTP/2 (et autres...)).
- parfois le navigateur web peut-être spécifiée pour indiquer au serveur web lequel on utilise. 
- "host": on dit au serveur web que nous voulons le site "exemple.ma"
- en dessous du "host": une ligne vide pour informer le serveur web que la requête est terminée


#### Les réponses:

Exemple:
![http_response.png](../../../_resources/http_response.png)

- La version du protocole HTTP
- Un code de statut, qui indique si la requête a réussi ou non.
- Un message de statut qui est une description rapide, informelle, du code de statut.
- Les **en-têtes** HTTP, comme pour les requêtes.
    Les en-têtes HTTP permettent au client et au serveur de transmettre des informations supplémentaires avec la requête ou la réponse.
	comme "server: Apache": le logiciel du serveur web et le parfois le numéro de version.
	la date actuels du serveur web.
	content-type: indique au client quel type d'informations va être renvoyée, comme du html, XML, images ....
	content-length: la durée de la réponse