
## Open System Interconnection

Le modèle #OSI, permet d'expliquer l'aspect théorique du fonctionnement des réseaux informatique.

En résumé, c'est le modèle TCP/IP mais en mieux expliquer/plus détailler.

Le modèle OSI se compose de 7 couches:

![[Pasted image 20240912221142.png]]
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

![[Pasted image 20240912221221.png]]

Lorsque le message est reçu par le 2 ordinateurs, il inverse le processus: en commençant par la couche physique et en remontant jusqu'à atteindre la couche application, en supprimant les informations ajoutées au fur et à mesure => c'est la désencapsulation.