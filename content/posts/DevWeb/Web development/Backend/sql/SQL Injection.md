# SQL Injection

Injection SQL (SQLi) = cyberattaque qui injecte du code SQL malveillant dans une application, permettant d'afficher ou de modifier une bdd. 

## Type d'injection SQL 

Injection SQL basée sur les erreurs.
Injection SQL basée sur l'union. 

## Injection SQL Inférentielle 

Injection Booléenne
Injection basée sur le temps

## Injection SQL hors bande 

## Bonne pratiques pour protéger les bdd contre l'injection SQL

- Installer logiciels et correctifs de sécurité 
- Donner aux comptes qui se connectent à la bdd uniquement les privilèges nécessaires
- Utilisez  la validation pour tout les types d'entrées fournies par l'utilisateur, y compris les menus déroulants. 
- Configurer le signalement des erreurs au lieu d'envoyer des messages d"erreur au navigateur Web client (ils peuvent être une vulnérabilité car ils exposent des informations sur la base de données.) Il faut donc désactiver les messages d'erreur après la mise en ligne d'un site web ou d'une application. 
- Regarder ce lien pour plus d'astuces. 
https://www.crowdstrike.com/cybersecurity-101/sql-injection/