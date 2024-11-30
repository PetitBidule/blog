La plupart du temps on attendra un évènement pour effectuer une action. Par exemple, nous allons déclencher une action lors d'un clic sur un élément particulier.
Pour faire cela on va avoir besoin d'utiliser un écouteur d'évènement grâce à la méthode ==addEventListener==.

La **méthode addEventListener() ** de **l'EventTarget** configure une fonction qui sera appelée chaque fois que l'évènement spécifié est envoyé à la cible.

> Les cibles courantes sont un <u>Element</u>, le <u>Document</u> lui même et une <u>Window</u>, mais on peut tout à fait cibler n'importe quel objet prenant en charge les évènements.

## Syntaxe:

> target.addEventListener(type, listener \[, options\]);

Paramètres:
Type:
Une chaîne sensible à la casse représentant le type d'évènement à écouter.
Listener:
L'objet qui recevra un évènement lorsqu'un évènement du type spécifié se produit. Cet argument doit être un objet implémentant l'interface ou une fonction JS.
Options:
Il est possible d'ajouter un troisième paramètre qui est un objet qui peut prendre 3 prpriétés 
- ==Once==, est un booléen permettant d'indiquer si l'évènement doit être écouté qu'une seule fois
- ==Passive==, est un booléen qui, si true, indique que la fonction spécifiée par listener n'appellera jamais preventDefault(). Certains évènements sont passifs par défaut et il faudra mettre cette valeur à **false** si vous rencontrez des erreurs 
- ==capture==, est un booléen qui indique si le **listener** doit être enregistrer avant d"être distribué aux éléments enfants. 

## Créer un écouteur:

```js
element.addEventListener("Type d'évènement", callback)
element.addEventListener('click', function(){
    window.alert('Vous avez cliqué sur le lien')
})
```

## <u>Exemple de différents type d'évènements:</u>

- ==MouseEvent:==
    L'interface MouseEvent représente les évènements qui se produisent lors d'une interaction de l'utilisateur avec un appareil de pointage.
- (...)

# L'évènement:

Le callback passé en second paramètre prend e paramètre l'évènement (le type de la variable dépendra de l'évènement écouté).
Exemple:

```js
element.addEventListener('click',function(e){
    e.proventDefault()
    e.stopPropagation()
    e.target()
    e.currentTarget()
})
```

- ==Event.preventDefault():==
    Cette méthode annule l'évènement s'il est annulable ce qui signifie que l'action par défaut qui appartient à l'évènement ne se produira pas.
    Cela peut-être utile lorsque vous cliquer sur le bouton d'un formulaire et l'empêcher de soumettre à cause d'un champ non remplis par exemple.
- ==Event.stopPropagation():==
Evite que l'évènement courant ne se propage plus loin dans les phases de capture et de déploiement.$
- ==EventTarget.addEventListen:==
EventTarget est une interface DOM implémentée par des objets qui peuvent recevoir des évènements et peuvent avoir des écouteurs pour eux.
- ==Event.currentTarget:==
Exemple:
````html
<button><span>Bonjour</span></button>
````
````js
const button = document.querySelector('button')
button.addEventListener('click', function(event){
	console.log(event.target, event.currentTarget)
})
// On obtient en console:
// <span>Bonjour</span> --> target
// <button>...</button> -->	currentTarget
````

