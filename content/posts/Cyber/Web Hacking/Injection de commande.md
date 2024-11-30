
L'injection de commande est l'abus du comportement d'une application pour exécuter des commandes sur le système d'exploitation, en utilisant les mêmes privilèges que ceux avec lesquels l'application s'exécute sur un appareil.

Les attaques par injection de commandes sont possibles lorsqu'une application transmet des données non sécurisées fournies par l'utilisateur (formulaires, cookies, en-têtes HTTP)
## Blind Method 

Ce type d'injection se produit lorsqu'il n'y a pas de sortie directe de l'application lors du test des charges utiles.

## Verbose Method 

Ce type d'injection se produit lorsqu'il y a un retour direct de l'application une fois qu'on a testé une charge utile.

## Correction de l'injection de commande

![[Pasted image 20240926142723.png]]

1 = L'application n'acceptera qu'un modèle spécifique de caractère 
2 = L'application va alors procéder uniquement à l'exécution de ces donneés qui sont toutes numériques.


fonction filter_input en php peut être utilisée pour vérifier si les données soumise s via un formulaire de saisie sont ou non nombre. S'il ne s'agit pas d'un nombre, il doit s'agir d'une entrée non valide.

![[Pasted image 20240926143003.png]]