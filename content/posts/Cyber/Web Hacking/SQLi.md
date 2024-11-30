Injection SQL (SQLi) = cyberattaque qui injecte du code SQL malveillant dans une application, permettant d'afficher ou de modifier une bdd.

## Type d'injection SQL

Injection SQL basée sur les erreurs.  
Injection SQL basée sur l'union.

## Injection SQL Inférentielle

Injection Booléenne  
Injection basée sur le temps

## SQLi en bande

SQL In-Band fait référence à la même méthode de communication utilisée pour exploiter la vulnérabilité et également recevoir les résultats.

## Blind SQLi

Contrairemrent à l'injection SQL en bande, où nous pouvons voir les résultats de notre attaque directement sur l'écran. Le SQLi aveugle se produit lorsque nous obtenons peu ou pas de retour d'information pour confirmer si les requêtes injectées ont réussi ou pas.

## Boolean Based Blind SQLi

L'injection SQL basée sur des booléens fait référence à la réponse que nous recevons de nos tentatives d'injection qui peut être un vrai/faux, oui/non, activé/désactivé, 1/0.

Exemple:

https://website.thm/checkuser?username=admin

La requête sql équivalente serait:
```sql
select * from  users where username = '%username%' limit 1;

```

![[20240926-1446-51.9819590.mp4]]



## Injection SQLi hors bande



## Bonne pratiques pour protéger les bdd contre l'injection SQL

- Installer logiciels et correctifs de sécurité
- Donner aux comptes qui se connectent à la bdd uniquement les privilèges nécessaires
- Utilisez la validation pour tout les types d'entrées fournies par l'utilisateur, y compris les menus déroulants.
- Configurer le signalement des erreurs au lieu d'envoyer des messages d"erreur au navigateur Web client (ils peuvent être une vulnérabilité car ils exposent des informations sur la base de données.) Il faut donc désactiver les messages d'erreur après la mise en ligne d'un site web ou d'une application.
- Regarder ce lien pour plus d'astuces.  
    [https://www.crowdstrike.com/cybersecurity-101/sql-injection/](https://www.crowdstrike.com/cybersecurity-101/sql-injection/ "https://www.crowdstrike.com/cybersecurity-101/sql-injection/")

## Assainissement 

Requêtes paramétrées
Validation des entrées 