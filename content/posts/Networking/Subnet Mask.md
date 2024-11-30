
Un masque de sous-réseau est un nombre qui ressemble à une adresse IP
Il révèle combien de bits de l'adresse IP sont utilisée pour le réseau en masquant la partie réseau de l'adresse IP 



![[Pasted image 20241125202356.png]]
IP to binary 

![[Pasted image 20241125201642.png]]
## Classe 

![[Pasted image 20241125200014.png]]


![[Pasted image 20241125200057.png]]

Dans un réseau avec un masque de sous-réseau /24 ou (255.255.255.0), il y a exactement 256 adresses IP possibles.
Explication:
Un masque /24 signifie que les 24 premiers bits sont utilisés pour l'adresse du réseau soit l'équivalent de la class C, et les 8 bits restants sont utilisée pour les hôtes.

- Une adresse est réservée pour l'identifiant du réseau 
- Une adresse est utilisée comme adresse de diffusion (broadcast)
Soit un total de 254 adresses dispo pour les hôtes.

Dans un réseau avec un masque de sous réseau /16 soit la class B, il y a environ 65 000 ip diso 
Dans un réseau avec un masque de sous réseau /8 encore plus 

## CIDR

Classless Inter-Domain Routing == est une méthode d'allocation d'addresse IP et de routage des paquets de protocole Internet de manière plus flexible et plus efficace

255.255.255.0 == /24  
=> to binary 
11111111.11111111.11111111 => 24 bits  => /24

