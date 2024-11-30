## CDN

CDN = Content Delivery Network / Réseau de diffusion de contenu

Groupe de serveurs répartis en de nombreux endroits. 
Généralement utilisés pour diffuser du contenu statique tel que Javascript, HTML, CSS, des images, des videos ... 
Ils mettent en cache le contenu du serveur d'origine et le diffusent aux user à partir du serveur CDN le plus proche de sorte que les demandes Users soient traitées plus rapidement.

![[Pasted image 20241106142457.png]]

## Proxy

Un serveur proxy agit comme intermédiaire entre un client demandant une ressource et le serveur fournissant cette ressource

https://www.youtube.com/watch?v=5cPIukqXe5w&ab_channel=PowerCertAnimatedVideos
## Load Balancers 

Load Balancers == Equilibreurs de charge. 

L'équilibreurs de charge permet de voir quel serveur est le plus apte à traiter la demande. 
Pour cela il utilise des algo, comme le **round-robin**, qui l'envoie à chaque serveur à tour de rôle, le **weighted**, qui permet de vérifier le nombre de demandes qu'un serveur traite actuellement et l'envoie au serveur le moins occupé. 


![[Pasted image 20240915155755.png]]
## WAF 

Un WAF (pare feu d'application web), se situe entre le requête web et le serveur web. 
Permet de protéger le serveur Web contre le piratage ou les attaques. 
Il analyse les requêtes Web pour détecter les techniques d'attaque courant

![[Pasted image 20240915160836.png]]

## Cache Web 

[[Web Cache Poisoning]]

Le cache se situe entre le serveur et l'utilisateur, où il enregistre (met en cache) les réponses à des requêtes particulières, généralement pendant une durée déterminée. 
Si un autre utilisateur envoie ensuite une requête équivalente, le cache fournit simplement une copie de la réponse mise en cache directement à l'utilisateur. 
Cela permet d'alléger la charge du serveur ne réduisant le nombre de requêtes en double qu'il doit gérer. 

![[Pasted image 20241106124517.png]]

Response HTTP:

X-Cache: hit -> Cela signifie que la demande a été traitée par le CDN et non par les serveurs d'origine. 

## Vulnérabilité Web 

[[Web Vulnérabilité]]
