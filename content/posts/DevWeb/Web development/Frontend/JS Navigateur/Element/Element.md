# Element

Element est la classe de base la plus générique dont héritent tous les objets qui représentent des éléments d'un Document.
Elle contient uniquement des méthodes et propriétés communes à l'ensemble des éléments.

# Propriétés d'instance

- ## element.classList:
    

La propriété en lecture seule Element.classList retourne une collection directe **DOMTokenList** des attributs de classe de l'élément.

**DOMTokenList**:

L'interface DOMTokenList représente un ensemble de marques séparées par un espace. On obtient un tel ensemble grâce aux propiétés **Element.classList**....
Les positions de cette liste sont numérotées à partir de 0.

### Méthodes:

- ==DOMTokenList.add()==, cette méthode ajoute la marque à la liste.
    Exemple:

```html
<span class="a b c"></span>
```

```js
let span = document.querySelector('span')
let a = span.classList.add('d')
span.textContent = a
// on obtient "a b c d"
```

- ==DOMTokenList.contains()==, cette méthode renvoie un boolean si la liste contient le symbole donné, sinon false.
    Exemple:

```html
<span class='a b c'></span>
```

```js
let span = document.querySelector('span')
let result = span.classList.contains("c")
if(result){
    span.textContent = 'The classList contains "c"'
}else {
    span.textContent = "The classList does not contain 'c'"
}
// on obtient "the classList contains 'c'"
```

- ==DOMTokenList.forEach()==, appelle le retour donné en paramètre, un pour chaque paire de valeurs dans le liste, dans l'ordre d'insertion.
    Exemple:

```html
<span class='a b c '></span>
```

```js
let span = document.querySelector('span')
let classes = span.classList
let iterator = classes.values()

classes.forEach(
function(value, key, listObj){ //value: l'élément en cours de traitement dans le tableau; key: L'index de l'élément en cours de traitement dans le tableau; listObj: le tableau que forEach est en train d'appliquer
    span.textContent += value + '' + key + '/' + this + '++'
}
    "arg"
)
// a 0/arg ++ b 1/arg++ c 2/arg++
```

- ==DOMTokenList.item()==, renvoie un élément de la liste par son index.
    Exemple:
    Le code html est le meme que les précédents.

```js
let span = document.querySelector('span')
let classes = span.classList
let item = classes.item(classes.length-1)
span.textContent = item
// c
```

- ==DOMTokenList.replace()==, remplace une marque existante par une nouvelle marque.
    Exemple:

```js
let span = document.querySelector("span")
let classes = span.classList
try{
    classes.replace('c', 'z')//c: la marque qu'on veut remplacer; z: la marque qui va remplacer l'ancienne
    span.textContent = classes
}catch(e){
    span.textContent = e
}
//  a b z
```

- ==DOMTokenList.toggle()==, supprime un jeton donné de la liste et renvoie false. Si le token n'existe pas, il est ajouté et la fonction renvoie true.
    Exemple:

```js
let span = docuement.querySelector('span')
let classes = span.classList

span.addEventListener('click', function(){
    let result = classes.toggle('c')
    
    if(result){
        span.textContent = `'c' ajouté; classList vaut désormais ${classes}.`
    }else{
        span.textContent = `'c' retiré; classList vaut désormais ${classes}`
    }
})
// classList vaut "a b" 
```