# Internet

## Qu'est ce qu'un réseau

Un réseau est un groupe d'ordinateurs ou d'autres appareils connectés les uns avec les autres.  
Tous ces réseaux, lorsqu'ils sont connectés ensemble, forment internet.

Internet est un réseau de réseaux.

## Comment fonctionne Internet

### Concepts de base et terminologie

Avant de commencer voyons certains concepts:

- Paquet: petite unité de données transmise sur Internet. (chaque paquet se voit attribuer un numéro de port).
- Routeur: appareil qui dirige les paquets de données entre différents réseaux  
    Exemple: fais tracert www.yahoo.com et tous les noms du style: ae77-0.ncidf104.rbci.orange.net sont des routeurs.
- Adresse IP: identifiant unique attribué à chaque appareil sur un réseau, utilisé pour acheminer les données vers la bonne destination.
- Nom de domaine: nom lisible par l'homme utilisé pour identifier un site web comme google.com
- DNS: Le Domain Name System est responsable de la traduction des noms de domaine en adresse IP.
- HTTP: Le protocole de transfert hypertexte utilisé pour transférer des données entre un clien et un serveur.
- HTTPS: version cryptée de HTTP utilisée pour fournir une communcation sécurisée entre un client et un serveur.
- SSL/TLS: les protocoles Secure Sockets Layer et Transport Layer Security sont utilisés pour assurer une communication sécurisée sur Internet.
- FAI: fournisseur d'accès Internet
- DHCP: Dynamic Host Configuration Protocol

* * *

Internet fonctionne en connectant des appareils et des systèmes informatiques entre eux à l'aide d'un ensemble de protocoles standardisés.

Ces protocoles définissent la manière dont les informations sont echangées entre les appareils et garentissent que les données sont transmises de manière fiable et sécurisée.

Lorsqu'on envoie des données sur Internet, elles sont divisées en petits paquets envoyés depuis notre appareils vers un routeur. Ce dernier examine le paquet et le transmet au routeur suivant sur le chemin vers sa destination.

Pour garantir que les paquets sont envoyés et reçus correctement, internet utilise divers protocole, notamment le protocole Internet (IP) et le protocole (TCP). IP est responsable du routage des paquets vers leurs destination correcte, tanids que TCP garantit que les paquets sont transmis de manière fiable et dans le bon ordre.

## Rôle protocole

Un protocole est une ensemble de règles et de normes qui définissent la manière dont les informations sont échangées entre les appareils et les systèmes.

Exemple de protocole:

- IP (protocole Internet)
- TCP (protocole de contrôle de transmission)
- UDP (le protocole de datagramme utilisateur)

## adresses IP & noms de domaine

Adresse IP = un identifiant unique attribué à chaque appareil sur un réseau. Il est utilisé pour acheminer les données vers la bonne destination prévu.  
Exemple: 192.168.1.1

Les noms de domaine sont des noms lisible par nous pour identifier des sites web.  
Les noms de domaine sont traduits en adresse IP à l'aide du système de nom de domaine (DNS).  
Exemple:  
Lorsqu'on saisie un nom de domaine dans notre navigateur, notre ordinateur envoie une requête DNS à un serveur DNS, qui renvoie l'adresse IP correspondante. Notre ordinateur utilise ensuite cette adresse IP pour se connecter au site web.

## TCP/IP

TCP/IP (Transmission Control Protocol/Internet Protocol)

Couche de protocoles d'application:  
Protocoles spécifiques aux applications telles que WWW, e-mail, FTP, etc...

Couche de protocole de contrôle de transmission:  
TCP: dirige les paquets vers une application spécifique sur un oridinateur à l'aide d'un numéro de port.  
TCP est responsable du routage des protocoles d'application vers la bonne application sur l'ordinateur de destination.

Couche de protocole Internet:  
IP: dirige les paquets vers un ordinateur spécifique à l'aide d'une adresse IP.  
Les paquets IP sont des entités indépendantes et peuvent arriver dans le désordre ou pas du tout. C'est le travail de TCP de s'assurer que les paquets arrivent et sont dans le bon ordre.

Couche matérielle:  
Convertit les données de paquets binaires en signaux réseau et inversement  
(Par exemple carte réseau Ethernet)

Concepts clés:

- Ports: Les ports sont utilisés pour identifier l'application ou le service exécuté sur un appareil. Chaque application ou service se voit attribuer un numéro de port unique, permettant aux données d'être envoyées vers la bonne destination.

## Hiérarchie de routage Internet

Les routeurs sont des commutateurs de paquets.  
Un routeur est généralement connecté entre les réseaux pour acheminer les paquets entre eux.  
Chaque routeur connaît ses sous-réseaux et les adresses IP qu'ils utilisent.

(Les boites noires sont les routeurs)

![e73baf40c71cfb9446cdb3098cc37187.png](../../_resources/e73baf40c71cfb9446cdb3098cc37187.png)

Lorsqu'un paquet arrive à un routeur, celui-ci examine l'adresse IP définie par la couche de protocole IP (on rappel que IP dirige les paquets vers un ordinateur spécifique à l'aide de l'adresse IP).  
Le routeur vérifie sa table de routage. Si le réseau contenant l'adresse IP est trouvé, le paquet est envoyé vers ce réseau. Si le réseau contenant l'adresse IP n'est pas trouvé, le routeur envoie le paquet sur une route par défaut, généralement en remontant la hiérarchie (en gro en remontant vers le haut) jusqu'au routeur suivant etc........  
Si ce n'est pas le cas, le paquet de donnée est à nouveau acheminé vers le haut jusqu'à ce qu'il atteigne un réseau fédérateur NSP.  
Les routeurs connectés aux NSP contiennent les plus grandes tables de routage et ici, le paquet sera acheminé vers le backbone approprié, où il commence son voyage inverse, en gro il fait le voyage vers le bas à travers des réseaux de plus en plus petits jusqu'a ce qu'il trouve sa destination.

## SSL/TLS

Concepts clés

- Certificats: Les certificats SSL/TLS sont utilisés pour établir la confiance entre le client et le serveur. Ils contiennent des informations sur l'identité du serveur et sont signés par un tiers de confiance (une Autorité de Certification) pour vérifier leur authenticité.
- Prise de Contact: pendant le processur de prise de contact SSL/TSL, le client et le serveur échangent des informations pour négocier l'algorithme de cryptage et d'autres paramètres pour la connexion sécurisée.
- Cryptage: une fois la connexion sécurisée établie, les données sont cryptées à l'aide de l'algorithme convenu et peuvent être transmises en toute sécurité entre le client et le serveur.