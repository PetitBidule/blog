# Adresse IP

Une adresse IP est un ensemble de nombres divisés en quatre octets.  
La valeur de chaque octet se résumera à l'adresse IP de l'appareil sur le réseau.

![505f805ff3eb71c20b743664abe3b30e.png](../../_resources/505f805ff3eb71c20b743664abe3b30e.png)

Une adresse publique est utilisée pour identifier l'appareil sur Internet, tandis qu'une adresse privée est utilisée pour identifier un appareil parmi d'autres appareils.

## Versions

Il existe 2 versions d'adresses IP:

- IPv4: utilise un systeme d'adressage 32 bits, permettant environ 4,3 milliards d'adresses IP uniques.  
    Exemple IPv4: 86.157.52.21
    
- IPv6: utilise un système d'adressage de 128 bits, fournissant un nombre nettement plus grand d'adresses IP disponibles (340 000 milliards).  
    Exemple IPv6: fe80::ef9c:23f6:41f4:bf80%5
    

# Sous Réseau

Permet de diviser un réseau en réseaux miniatures plus petits au sein de lui même.

![befec91797184e16c78a9484259fa3d2.png](../../_resources/befec91797184e16c78a9484259fa3d2.png)

Masque de sous réseau: nombre que 4 octets, allant de 0 à 255.

# Adresse mac

Les appareils sur un réseau auront tous une interface réseau physique, qui est une carte à puce trouvée sur la carte mère de l'appareil. Cette interface réseau se voit attribuer une adresse unique en usine = adresse MAC

# Protocole ARP (Address Resolution Protocol)

Le protocole ARP permet à un appareil d'associer son adresse MAC à une adresse IP sur le réseau.

# Protocol DHCP (Dynamic Host Configuration Protocol)

DHCP est protocole de gestion de réseau utilisé sur les réseau IP pour attribuer automatiquement des adresse IP et d'autres paramètes de communication aux appareils connectés au réseau.

![c2295ca7434747b849757fb5e178ea85.png](../../_resources/c2295ca7434747b849757fb5e178ea85.png)


## UDP (User Datagram Protocol)

Protocole sans connexion, convient sur des requêtes rapides, comme DNS ...

Pas poignée de main comme le TCP protocole pour établir la connexion, les connexions UDP reposent sur l'envoie de paquets vers un port cible et essentiellement sur l'espoir qu'ils y parviennent.  
UDP idéal pour la vitesse plutôt que la qualité (partage de vidéos)


# Modèle OSI (Open System Interconnection)

Le modèle OSI, permet d'expliquer l'aspect théorique du fonctionnement des réseaux informatique.

En résumé, c'est le modèle TCP/IP mais en mieux expliquer/plus détailler.

Le modèle OSI se compose de 7 couches:

![b727bfb203c2202797bc0a2c61860e1d.png](../../_resources/b727bfb203c2202797bc0a2c61860e1d.png)

Moyen mnemotechniques pour retenir: "Ah Petite Salope, Tu Recraches La Purée". (trop marrant).

## Explication de chacune des couches:

- Applicaton
- Présentation: Cette couche permet de formater les données reçu de la couche application
- Session: Cette couche permet d'établie la connexion entre 2 appareils
- Transport: Cette couche choisi entre 2 protocoles: TCP ou UDP, puis divise la transmission en petits morceau, ce qui facilite la transmission du message.
- Réseau: Localise la destination de la demande.
- Liaison: Ajoute l'adresse MAC à l'adresse IP reçu dans le paquet de la couche réseau.
- Physique: Convertit les données binaire en signaux et de les transmettre à travers le réseau.

## Encapsulation

Au fur et à mesure que les données sont transmises à chaque couche du modèle, d'avantage d'informations contenant des détails spécifique sont ajoutées. => c'est l'encapsulation.

![eb350927226565a50e2796ac23abd8e7.png](../../_resources/eb350927226565a50e2796ac23abd8e7.png)

Lorsque le message est reçu par le 2 ordinateurs, il inverse le processus: en commençant par la couche physique et en remontant jusqu'à atteindre la couche application, en supprimant les informations ajoutées au fur et à mesure => c'est la désencapsulation.

# TCP/IP (advanced)

Le modèle TCP/IP se compose de 4 couches:  
![66ae5fddf45a4e8fafdf66d343b41b56.png](../../_resources/66ae5fddf45a4e8fafdf66d343b41b56.png)  
Le processus d'encapsulation et desencapsulation marche aussi sur ce modèle.

## TCP

Protocole TCP est basée sur la connexion, donc avant d'envoyer des données, il faut établir une connexion entre les 2 ordinateurs.

Le processus pour mettre en place cette connexion est appelée "poignée de main à trois".

<img src="../../_resources/5515a6cc924096933e21b67a9cf9294c.png" alt="5515a6cc924096933e21b67a9cf9294c.png" width="581" height="416" class="jop-noMdConv">

Pour résumé, le client (l'ordinateur voulant établir une connexion) fait une requête contenant un bit SYN au serveur, ce dernier répondra un paquet contenant le bit SYN envoyer par le client plus un autre bit appelée ACK. Enfin le client renverra un paquet contenant juste la ACK envoyer par le serveur. Ceci terminée les données peuvent être transmises de manière fiable entre les 2 ordinateurs.

Dans le cas ou la connexion échouerait le serveur répondrait avec l'indicateur RST.  
![d05ee33d291766830928cf8a763d0b72.png](../../_resources/d05ee33d291766830928cf8a763d0b72.png)





# NFS 

NFS == Network File System, permet à un système de partager des répertoires et des fichiers avec d'autres sur un réseau. 
Pour résumer, il s'agit d'un system de fichiers qui permet aux utilisateurs d'accéder aux fichiers et répertoires situés sur des ordi distants et de traiter ces fichiers et répertoires comme s'ils étaient locaux. 
