# LocalStorage:

Le ==localStorage== permet de sauvegarder des informations dans la mémoire du navigateur afin de faire persister les informations meme si l'utilisateur quitte la page ou ferme son navigateur. (ne nécessitent pas d'être envoyées au serveur à chaque requête comme les cookies).

## Méthode setltem():

#### Syntaxe:

> storage.setItem(nomClé, valeurClé);

````js
localStorage.setItems('todos', JSON.stringify(todos))
````

On pourra ensuite récupérer cette information dès qu'on le souhaite dans notre page avec la méthode ==getItem()==

#### Syntaxe 
>getItem(key)

````js
const todoInStorage = localStorage.getItem('todos')
const todos = todosInStorage ? JSON.parse(todosInStorage): []
````
<u>/!\ Pour Rappel:</u>
La méthode **JSON.stringify()** convertit une valeur JS en chaîne JSON. Optionnellement, elle peut remplacer des valeurs ou spécifier les propriétés à inclure si un tableau de propriétés a été fourni.
La seule différence sera que les noms des objets seront entre guillemets.
Exemple:
````js
console.log(JSON.stringify({x:5, y:6}));
// On obtient: "{"x":5, "y":6}"
````
/!\ Fin du Rappel:

## Méthodes clear():

La méthode **clear()** de l'interface Storage, lorsqu'elle est invoquée vide toutes les clés stockées.

## Méthodes removeItem():

La méthode **removeItem()** de l'interface Storage, lorsque vous lui passez une clé en argument, va supprimer la ressource avec le nom de clé correspondant
Si aucun élément n'est donné en paramètre **nomClé**, cette méthode ne fait rien.

#### Syntaxe:
> removeItem(nomCle)

## Méthodes .key():

La méthode **key()** de l'interface Storage prend un nombre n en argument et retourne la n-ième clé contenue dans storage. L'ordre des clés étant définie par le navigateur, il est recommandé de ne pas s'y référer

#### Syntaxe:
>.key(cle)

# SessionStorage:


|   | LocalStorage |SessionStorage |
| ------------- | ------------- |-------|
| Aucun date d'expiration | Oui  | Oui	|
| Attaché à l'origine | Oui |	Oui|
| Disponible dans plusieurs onglets ou fenêtre  | Oui  | Non	|
| Survit au rafraîchissement d'une page  | Oui  |	Oui |
| Survit à la fermeture d'un onglet ou d'une fenêtre  | Oui  | Non	|
| Survit au redémarrage de l'ordinateur  | Oui  |Non|















