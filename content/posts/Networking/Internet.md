Un réseau est un groupe d'ordinateurs ou d'autres appareils connectés les uns avec les autres.  
Tous ces réseaux, lorsqu'ils sont connectés ensemble, forment internet.

Internet est un réseau de réseaux.

## Comment fonctionne Internet

### Concepts de base et terminologie

Avant de commencer voyons certains concepts:

- Paquet: petite unité de données transmise sur Internet. (chaque paquet se voit attribuer un numéro de port).
- [[Routeur]]: appareil qui dirige les paquets de données entre différents réseaux  
    Exemple: fais tracert www.yahoo.com et tous les noms du style: ae77-0.ncidf104.rbci.orange.net sont des routeurs.
-  [[Adresse IP]]: identifiant unique attribué à chaque appareil sur un réseau, utilisé pour acheminer les données vers la bonne destination.
- Nom de domaine: nom lisible par l'homme utilisé pour identifier un site web comme google.com
- [[DNS (Advanced)]]: Le Domain Name System est responsable de la traduction des noms de domaine en adresse IP.
- HTTP: Le protocole de transfert hypertexte utilisé pour transférer des données entre un client et un serveur.
- HTTPS: version cryptée de HTTP utilisée pour fournir une communcation sécurisée entre un client et un serveur.
- SSL/TLS: les protocoles Secure Sockets Layer et Transport Layer Security sont utilisés pour assurer une communication sécurisée sur Internet.
- FAI: fournisseur d'accès Internet
- [[Protocol DHCP]]: Dynamic Host Configuration Protocol



Internet fonctionne en connectant des appareils et des systèmes informatiques entre eux à l'aide d'un ensemble de protocoles standardisés.

Ces protocoles définissent la manière dont les informations sont echangées entre les appareils et garentissent que les données sont transmises de manière fiable et sécurisée.

Lorsqu'on envoie des données sur Internet, elles sont divisées en petits paquets envoyés depuis notre appareils vers un routeur. Ce dernier examine le paquet et le transmet au routeur suivant sur le chemin vers sa destination.

Pour garantir que les paquets sont envoyés et reçus correctement, internet utilise divers protocole, notamment le protocole Internet (IP) et le protocole ([[TCP - IP]]). IP est responsable du routage des paquets vers leurs destination correcte, tanids que TCP garantit que les paquets sont transmis de manière fiable et dans le bon ordre.
(Plus de détail dans le dossier protocole)