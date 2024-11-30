# Promise

L'objet Promise (pour "promesse en français") est utilisé pour réaliser des traitements de façon asynchrone. Une promesse représente une valeur qui peut-être disponible maintenant, dans le futur voire jamais.

Une promesse se construit avec une fonction qui recevra 2 **callbacks** que l'on pourra appeler en cas de succès ou d'échec de la logique.

### Rappel sur les fonction de rappel (callback):

Une fonction de rappel est une fonction passée dans une autre fonction an tant qu'argument, qui est ensuite invoquée à l'intérieur de la fonction externe pour accomplir une sorte de routine ou d'action.

Exemple:

```js
function salutation(name){
    alert ('Bonjour' + name);
}
function processUserInput(callback){
    let name = prompt('Entrez votre nom');
    callback(name);
}
processUserInput(salutation)
```

### Fin Rappel

Reprenons sur les promesse:
Exemple:

```js
function wait (duration){
    return new Promise((resolve, reject) =>{
        setTimeout(()=> resolve(duration), duration)
    })
} 
```

Une promesse peut être dans un de ces 3 états:

- pending (en attente): état initial, la promesse n'est ni remplie, ni rompue;
- fulfilled (tenue): l'opération a réussi;
- rejected (rompue): l'opération a échoué

On pourra utiliser 3 méthodes pour suivre la résolution de la promesse.

- ==**.then(callback)**==, si la promesse a été résolue.
    La then méthode prend jusqu'à 2 arguments: *then* sera appelé si la promesse est tenue.
    Exemple:

```js
const promise1 = new Promise((resolve, reject)=>{
    resolve("Succes")
})
promise1.then((value)=>{
    console.log(value);
})
// on obtient: "Succes"
```

- ==**.catch(callback)**==, si la promesse a échoué.
    La catch méthode permet de planifié l'appel d'une fonction lorsque la promesse est rejeté.
    (pour simplifier *catch* sera appelée si la promesse est rompue).
    Exemple:

```js
const promise1 = new Promise((resolve, reject) = >{
    throw 'Uh-oh!'
});
promise1.catch((error)=>{
    console.error(error);
})
// on obtient: "Uh-oh:"
```

- ==**.finally(callback)**==, si la promesse a échoué ou a été tenue.
    Il sera appelé quoi qu'il arrive.
    Exemple: (pas ouf mais bon c'est tjrs ça)

```js
function checkMail(){
    return new Promise((resolve, reject)=>{
        if (Math.random()>O.5){
            resolve('Mail has arrived');
        }else{
            reject(new Error('Failed to arrive'))
        }
    })
}
checkMail()
    .then((mail)=>{
    console.log(mail)
})
    .catch((err)=>{
    console.error(err)
})
    .finally(()=>{
    console.log('Experiment completed')
})
```

# Await & Async

Une méthode peut être déclarée comme asynchrone grâce au mot clef **aync**. Dans ce cas, le retour de la fonction sera une promesse.

Exemple:

```js
async function maFonction (){
    return 4
}
console.log(maFonction())
//Promise {<fulfilled>:4}
```

Dans une fonction asynchrone il est possible d'utiliser le mot clef **await** pour attendre la résolution d'une Promise et obtenir la résultat.
Exemple:

```js
async function maFonction(){
    const response = await autreFonctionAsynchrone()
    return response.data
}
```

Si la Promise du await échoue on pourra capturer l'erreur à l'aide de la syntaxe **try...catch** classique.
Exemple:

```js
async function maFonction(){
    try{
        const response = await autreFonctionAsynchrone()
        return response.data
    }catch (e){
        (...)
    }
}
```