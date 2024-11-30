
## Adresses MAC

Les périphériques d'un réseau possèdent tous une interface réseau physique, qui est une carte à puce intégrée à la carte mère du périphérique. Cette interface réseau se voit attribuer une adresse unique dans l'usine où elle a été construite, appelée adresse MAC 

Exemple:
(6 groupes de 2 caractères chacun, séparés par 2 points).
**00:1B:44:11:3A:B7**


Le protocole ARP (Address Resolution Protocol) permet à un appareil d'associer son adresse MAC à une adresse IP sur le réseau., afin que les données puissent être renvoyées directement au bon destinataire au sein du réseau local. 

Il est chargé de trouver l'adresse MAC associé à une adresse IP spécifique.

(Une adresse MAC == adresse physique est un identifiant physique stocké dans une carte réseau)

![[Pasted image 20240912214227.png]]

Vulnérabilité 

**ARP Spoofing/ARP Poisoning** : Une attaque courante dans laquelle un attaquant envoie de fausses réponses ARP, associant une adresse IP légitime à sa propre adresse MAC, permettant ainsi de rediriger ou d'intercepter les données destinées à un autre appareil.