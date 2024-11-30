

Cross-Site Scripting, attaque par injection où du Javascript malveillant est injecté dans une application Web avec l'intention d'être exécutée par d'autres utilisateurs. 

![[Pasted image 20241106113834.png]]
## Reflected XSS

Le XSS réfléchi se produit lorsque les données fournies par l'utilisateur dans une requêtes HTTP sont incluses dans la source de la page web sans aucune validation. 

Exemple:

![[Pasted image 20240925214446.png]]

L'application ne vérifie pas le contenu du paramètre d'erreur, ce qui permet à l'attaquant d'insérer du code malveillant.
![[Pasted image 20240925214510.png]]


## Stocked XSS

(XSS est stocké sur l'application Web (dans une base de données, par exemple) et est ensuite exécutée lorsque d'autres utilisateurs visitent le site.)
Survient lorsqu'une application reçoit des données d'une source non fiable et inclut ces données dans ses réponses HTTP ultérieures 

## XSS basé sur DOM 