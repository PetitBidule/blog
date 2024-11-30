## LFI 

L'inclusion de fichiers locaux (LFI) est une vulnérabilité de sécurité qui se produit lorsqu'une appli web permet aux utilisateurs d'inclure des fichiers du système de fichiers local. 

Les attaquants exploitent LFI en manipulant les champs de saisie pour récupérer des fichiers sensibles ou exécuter du code malveillant (RCE).

Fonction PHP vulnérable:
require, require_once, include, include_once.

Outils:
https://github.com/kurobeats/fimap
fimap, outil en python pour trouver les bogues de fichiers locaux et distants dans les applications.
### Exemple:

![[Pasted image 20240926183000.png]]

Tout d'abord, l'utilisateur envoie une requête HTTP au serveur web qui inclut un fichier à afficher. 
Dans notre cas, pouvoir accéder à son cv, dans la requête peut prendre en paramètre le 'userCV.pdf', donc le fichier auquel l'utilisateur veut accéder.

### Octet nul (%00)

Contourner l'ajout de caractères supplémentaires à la fin de chaîne fournie 
Exemple:
"http://example.com/index.php?page=../../../etc/passwd%00"
(ceci est résolu depuis PHP 5.4)

### Technique de troncature de chemin

La troncature de chemin est une méthode utilisée pour manipuler les chemins d'accès aux fichiers dans les applications web. 
Elle est souvent utilisée pour accéder à des fichiers restreints en contournant certaines mesures de sécurité qui ajoutent des caractères supplémentaires à la fin des chemins d'accès aux fichiers.
L'objectif est de créer un chemin d'accès au fichier qui, une fois modifié par la mesure de sécurité, pointe toujours vers le fichier souhaité.

#### Exemple en PHP:

/etc/passwd, /etc/passwd, /etc/./passwd, et /etc/passwd/  sont tous traités comme le même chemin. 

d'autre tips sur https://book.hacktricks.xyz/pentesting-web/file-inclusion

### A partir d'un dossier existant 

Peut-être que le back-end vérifie le chemin du dossier:
"http://example.com/index.php?page=utils/scripts/../../../../../etc/passwd";


## RFI

L'inclusion de fichier a distance est une technique permettant d'inclure des fichiers distants dans une application vulnérable. 
RFI se produit lors d'une désinfection incorrecte de la saisie de l'utlisateur
Condition requise: l'option "allow_url_fopen" doit être activé 
=> allow_url_fopen est une option de configuration de php qui permet d'ouvir des fichiers distants via des urls. 

Les conséquences d'une attaques RFI sont:
- Divulgation d'informations sensibles
- script instersite soit XSS
- déni de service DoS


### Exemple:

Pour qu'une attaque RFI puisse fonctionner, il faut qu'un serveur externe puisse communiquer avec le serveur d'applications. L'attaquant héberge alors des fichiers malveillants sur son serveur. Le fichier malveillants est ensuite injecté dans la fonction include via des requêtes HTTP et le contenu du fichier malveillant s'exécute sur le serveur d'applications vulnérable. 
![[Pasted image 20240926184023.png]]
python -m http.server 8000