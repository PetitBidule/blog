
## .gitignore 

Les fichiers ignorés sont suivis dans un fichier spécial nommé ".gitignore" qui est enregistré à la racine de votre référentiel. 

## Merge Strategies 

### Fast-Forward (FF)

Pour faire simple:
Fast-Forward permet de mettre a jour une branche sans créer de nouveau commit de fusion à condition que la branche à fusionner est linéairement derrière la branche cible 

Exemple:
````
# Avant Fast-Forward

main:        A --- B
feature-branch:     \C --- D 

## Après Fast-Forward

main: A --- B --- C --- D

````
```
```
L'historique reste simple

### Non-Fast-Forward (No-FF)

A l'inverse le non fast forward crée un commit de fusion, s'il n'est pas possible de simplement avancer le pointeur, car la branche cible a des commits qui ne sont pas présents sur la branche à fusionner.
(Il y a des commits dans la branche cible qui ne sont pas dans la branche à fusionner)

--no-ff crée un commit supplémentaire. On peut facilement vérifier ce qui se passe dans l'historique et supprimer une nouvell fonctionnalité. 
https://gist.github.com/moraisaugusto/1fa02c49b6d9833fcdf665505595ac2e

no-ff a gauche et ff a droite
![[Pasted image 20240929002214.png]]


## Squash 

Le Squashing fait référence au processus de combinaison de plusieurs commits en un seul. Cela est souvent fait pour créer historique de commits plus propre. 

## Cherry Picking Commits

Le cherry-picking dans Git permet d'appliquer un commit spécifique d'une branche à une autre, sans fusionner la branche entière. 
https://www.atlassian.com/git/tutorials/cherry-pick

## Git Stash 

Permet d'enregistrer temporairement les modifications lorsqu'elles ne sont pas encore prêtes à être validées 

- git stash apply
- git stash apply "stash name"
- git stash pop


## Annuler les modifications 

### Git Reset

Réinitialise la branche à un commit précédent. Il est essentiel de spécifier l'un des trois modes: 
soft, hard ou mixed. 
#### Soft

Dans ce mode, seul le pointeur HEAD est déplacé vers le commit spécifié. Les fichiers du répertoire de travail ne sont pas modifiés.

#### Hard
#### Mixed

### Git Revert

Crée un nouveau commit qui annule les modifications spécifiées 