# Fetch

La méthode fetch() permet de faire des appels HTTP afin de récupérer des ressources sur le réseau et utilise le système de promesse.

Le premier paramètre sera souvent une chaîne de caractère indiquant m'URL de la ressource à aller récupérer et le second paramètre sera un objet d'options spécifiant les informations à envoyer avec la requête.

Exemple

```js
fetch('https://jsonplaceholder.typicode.com/posts?_limit=10')
    .then(r => console.log("La réponse",r))
```

La promesse est résolue avec un objet **Response**
(voir mdn pour plus d'info).
Cet objet contiendra notamment une propriété *ok* qui sera vraie.
Exemple:

```js
fetch('https://jsonplaceholder.typicode.com/posts?_limit=10',{
    headers:{
        Accept : 'application/json'
    }
})
    .then(r => {
        if(r === ok){
            return r.json()
        }else{
            throw new Error('Erreur serveur')
        }
})
    .then(posts => {
        console.log('La liste des articles:', posts)	
})
    .catch(e => {
    console.log.error('Une erreur est survenue', e)
})
```

## Les interfaces de Fetch

La méthode fetch() est utilisée pour récupérer une ressource

Dans le code ci-dessus, nous avons utilisé l'interface **headers** qui représente les en-têtes de requête et de réponse, cela nous permet d'effectuer diverses actions sur les en-têtes de requête et de réponse HTTP.

* * *

Nous avons aussi l'interface **Request** qui représente une demande de ressource.

* * *

Et enfin, l'interface Response qui représente la réponse d'une requête initialisée.

## Interrompre un fetch

Pour interrompre un fetch, nous aurons besoin des interfaces <u>==**AbortController**==</u> et <u>==**AbortSignal**==</u>, elles autorisent les opérations telles que Fetch à être interrompue si elles ne sont pas encore achevées.

- L'interface AbortController représente un objet contrôleur qui pemet d'abandonner une ou plusieurs requêtes.
- L'interface AbortSignal représente un objet signal qui vous permet de communiquer avec une requête DOM et de l'annuler si nécessaire par un objet AbortController

Exemple:

```js
const a = new AbortController()
Promise.race([
    fetch('https://jsonplaceholder.typicode.com/posts?_limit=10',{
        signal: a.signal
})
    fetch('https://jsonplaceholder.typicode.com/posts?_limit=10',{
        signal: a.signal
    })
]).then(r => r.json()).then(console.log)
```

