# Redux 

Redux est une bibliothèque de gestion d'état pour les applications JS
Redux aide à centraliser et à gérer l'état de ton application en suivant un flux de données prédictible.

## Actions Redux 

Les actions redux décrivent comment faire quelque chose. 
Dans redux, une action est un simple objet JS qui explique l'action à effectuer sur notre état afin de le manipuler. 

Exemple d'action Redux: 
```` javascript 

const action = {
	type: "MANGER_UN_KIWI"
}

````

- Les actions Redux auront TOUJOURS une propriété TYPE décrivant quoi faire
- Le type d'actions est écrit en lettre majuscules; 
- L'actions redux, peux avoir une propriété payload, qui peut donner des détails sur l'action
Exemple 
````javascript

const action = {
  type: 'BUY_APPLES',
  payload: {
    shop: 'Simba supermarket',
    type: 'red',
    number: 10,
  }
};

````

---
## Réducteurs Redux 

Un réducteur est une fonction pure qui prendra l'état initial et l'action souhaitée, effectuera l'action souhaitée et renverra un état mis à jour. 

Un réducteur doit être pur pour qu'il marche toujours de manière cohérente. 

Exemple de réducteurs:

````javascript 
const state = {
	count: 0
}

const incrementAction = {
	type: "INCREMENT"
}

const decrementAction = {
	type: "DECREMENT"
}
const reducer = (state, action)=>{
  switch(action.type) {
	  case 'INCREMENT': {
		  const newState = { ...state };
		  newState.value = state.value + 1;
		  return newState;
	  } 
	  case "DECREMENT": {
		  const newState = { ...state };
		  newState.valur = state.value - 1;
		  return newState;
	  }
  }
}
````

explication:

- const newState = { ...state }: un réducteur est une fonction pure et ne mutera jamais l'état qui lui est passé en argument. 
On crée un nouvel objet et copions l'état précédent à l'aide du spread syntax 
---
## Selecteurs

Les sélecteurs 

---
## Redux store

Lorsque nous mettons à jour l'état avec la fonction de réduction, le nouvel état remplace l'ancien état.

C'est redux store, c'est comme un magasin réel qui conserve des enregistrements de la façon dont l'état change dans l'application. 

Pour créer ce magasin, on utilise la fonction createStore(), cette dernière fournit d'autres fonctions pour manipuler l'état.

Exemple:
````javascript
import { configureStore } from '@reduxjs/toolkit'

const store = configureStore({ reducer: counterReducer })

console.log(store.getState())
// {value: 0}
````

Nous avons par exemple: 

- getState(): lorsqu'on execute cette fonction, le magasin renverra la valeur actuelle de l'état et cette valeur sera toujours l'état mis à jour. 
- dispatch(): on transmet l'action à la dispatch fonction, et la magasin aura accès au réducteur et à l'état lui-même et il fera tout pour toi. 
---
## Quand utiliser redux 

- L'état de l'application est fréquemment mis a jour au fil du temps.
- La logique pour mettre à jour cet état peut être complexe 
- L'application dispose d'une base de code taille moyenne ou grande et peut êtr utilisée par de nombreuses personnes.
- Tu disposes d'une grande quantité d'états d'application qui sont nécessaires à de nombreux endroits de l'application. 
---
## Gestion de l'état 

![0b3745c6ce2de8589af30bbb3cd1dfb8.png](../_resources/0b3745c6ce2de8589af30bbb3cd1dfb8.png)

- L'état décrit l'état de l'application à un moment précis
- L'interface utilisateur (UI) est rendue en fonction de cet état 
- Lorsque quelque chose se produit (action fait par l'utilisateur), l'état est mis à jour en fonction de ce qui s'est passé. 
- L'UI est restituée en fonction du nouvel état. 

Le problème est que si plusieurs composant doivent partager le même état ça devient plus complexe. 

Solution: 

Cette solution consiste à extraire l'état partagé des composants et à le placer dans un "emplacement centralisé" en dehors de l'arborescence des composants. 
Ainsi, chaque composant peut accéder à l'état ou déclencher des actions peu importe ou il se trouve dans l'arborescence. C'est redux. 





