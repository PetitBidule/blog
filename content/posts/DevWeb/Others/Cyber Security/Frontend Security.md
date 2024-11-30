# Frontend Security

## XSS

## SQL Injections

## Cross Site Request Forgery

## A Man-in-the-Middle

## Clickjacking

## Security Misconfiguration Attacks

## Dependency Exploitation 

## CSP 

Politique de sécurité du contenu est une couche de sécurité supplémentaire qui permet de détecter et d'atténuer certains types d'attaques comme les attaques XSS et SQLI 

## IDOR (Insecure Direct Object Reference)

## Défaillance Cryptographique 


# Cryptographie

La cryptographie est uitlisée pour protéger la confidentialité, garantir l'intégrité et garantir l'authenticité. 

## Hexadecimal == base16

Utilisé pour désigner un système de numérotation en base 16. 
Les nombres sont représentés en utilisant les chiffres de 0 à 9 et les lettre de 1 à F 

## Base 16 == Hexadecimal

Base 16 signifie simplement que le système utilise 16 symboles différents pour représenter les valeurs. 


## Base 32

La base 32 utilise un ensemble de 32 symboles pour représenter les nombres. 
Caractéristiques:
lettres majuscules de A à V
chifffre de 0 à 9

utile:
moins de symbole.
## ROT13 

un algo de chiffrement de texte, il s'agit d'un décalage de 13 caractères de chaque lettres du texte à chiffrer.

![1966a2f17199f0f2bf22c859d264cfc2.png](../../_resources/1966a2f17199f0f2bf22c859d264cfc2.png)



## Encryption 

- Ciphertext = résultat du cryptage d'un texte en clai et de donnée chiffrées
- cipher = méthode de chiffrement ou de déchiffrement de données. 
- paintext = Donnée avant chiffrement, souvent du texte, mais pas toujours. 
- encryption = Transformation de données en texte chiffré, à l'aide d'un chiffrement 
- encoding = Pas une forme de cryptage, juste une forme de représentation de donnée comme la base 64. Immédiatement réversible.
- key = Certaines informations nécessaires pour déchiffrer correctement le texte chiffré et obtenir le texte en clair.
- passphrase (phrase secrète) = Séparée de la clé, une phrase secrète est similaire à un mot de passe et utilisé pour protéger une clé.
- Asymmetric encryption = Utilise des clés différentes pour crypter et décrypter.
- Symmectric encryption = Utilise la même clé pour crypter et décrypter.
- Brute force = Attaquer la cryptographie en essayant chaque mot de passe différent ou chaque clé différente
- Cryptanalysis = Attaquer la cryptographie en trouvant une faiblesse dans les mathématique sous-jacentes.



## Metasploit 

Def:

- Exploit: morceau de code qui utilise une vulnérabilité présente sur le système cible.
- Vulnérabilité: défaut de conception, de codage ou de logique affectant le système cible.
- Charge utile (payload): un exploit exploitera une vulnérabilité. Cependant, si nous voulons que l'exploit ait le résultat souhaité, nous devons utiliser une charge utile. Les charges utiles sont le code qui s'éxecutera sur le système cible. 

- Encodeurs: permet d'encoder l'exploit et la charge utile dans l'espoir qu'une solution antivirus basée sur les signatures puisse les manquer. 
- Evasion: 


paramètres:

RHOSTS : "Hôte distant", l'ip du système cible. 
RPORT: "port distant", le port sur le système cible sur lequel l'application vulnérable s'exécute.
Payload: la charge utile qu'on utilise avec l'exploit.
LHOST: "localhost", l'ip de la machine qui attaque
LPORT: "Port local", le port qu'on utilise pour que le shell inversé se reconnecte. (Il s'agit d'un port sur la machine attaquante, le définir sur n'importe quel port non utilisé par une autre application).
SESSION: chaque connexion établie avec le système cible à l'aide de Metasploit aura un identifiant de session.
CONCURRENCY: Nombre de cibles à analyser simultanément
PORTS: plage de ports à analyser, entre 1 à 10000 xD
THREADS: nombre de threads qui seront utilisés simultanément. Plus il y en a plus c'est rapides. 