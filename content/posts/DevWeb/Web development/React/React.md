# React

## Hooks

Dans react, useState ainsi que toute autre fonction commençant par "use", est appelé un Hook.
Les hooks sont des fonctions spéciales qui ne sont disponibles que pendant le rendu de React. Ils permettent de se connecter à différentes fonctionnalités de React. 

Conventions d'écriture:
````react
const [someting, setSomething] 
````

Exemple:
````React 
const [index, setIndex] = useState(0);

function handleCLick(){
	setIndex(index + 1);
}
````

index = variable d'état avec la valeur qu'on stocke.
setIndex = fonction de définition d'état qui peut mettre à jour la variable d'état et déclencher React pour restituer le composant.

Une variable d'état pour conserver les données entre les rendus