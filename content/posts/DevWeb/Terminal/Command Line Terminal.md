pwd: afficher le répertoire courant  

ls: les différents dossier et fichier présent dans le répertoire  
ls -la: afficher les stats  
ls -a: fichiers et dossiers cachés  
ls -l: ajoute de nombreuses infos  

cd: te fais avancer dans le dossier de ton choix  
cd..: retounrne dans le dossier parent  

touch: crée un nouveau fichier  
mkdir: crée un nouveau dossier  

mv: déplacer du contenu, 2 paramètre l'élément à déplacer et la destination  
cp: copier, 2 paramètre le ficher à copier et la destination.  
rm: supprimer le fichier et rm -r pour supprimer un dossier  

cat: connaitre le contenu du fichier  
head: affiche les première ligne d'un fichier 
tail: affiche les dernière lignes d'un fichier 

find: recher des fichiers et des répertoires 
gzip: compressez les fichiers
gunzip: décompressez les fichiers compressés avec gzip
zip: créer ou extrayer des archives zip
unzip: extraire les fichiers d'une archive zip

wget: télécharger des fichiers depuis le web
curl: transférer des données depuis ou vers un serveur en utilisant divers protocoles

history: affiche l'historique des commande 

ps: afficher les processus en cours 
kill: terminer les processus 

less: comme man  
man: afficher le manuel d'une commande  

netstat: affiche les connexion réseau, les tables de routage et les statistique d'interface

more: ancienne version de less  
grep: chercher des éléments à l'intérieur d'un fichier  

cal: affiche un calendrier

cut:  
sed:  
awk:  
sort:  
chmod:  
systemctl:  
whoami:

### redirection

">"  
">>"  
"2>"

\*: caractère utilisé comme subsitut pour n'importe quel caractère dans une recherche

## Fonctionnement vi:

dd: supprimez la ligne  
yy: copiez  
p: collez  
esc: mode commande  
i: mode saisie  
r: remplacez une lettre  
cw: remplacer un mot  
shift+o: mettre une ligne au dessus  
w: déplacer de mot en mot  
b: la meme mais inverse  
x: supprime le caractère  
a: insertion de texte après le curseur