# Date:

Les objets JS **Date** représentent un instant donné sur l'axe du temps dans un format indépendant de la plateforme utilisée.
Les objets Date contiennent un nombre ( <small>number</small> ) qui représente le nombre de millisecondes écoulées depuis le premier janvier 1970 sur l'échelle <u>UTC</u>.

<u>UTC</u>: Temps universel coordonnée ou (UTC) est une échelle de temps adoptée comme base du temps civil international par la majorité des pays du globe.

## Constructeur Date():

Crée une instance d'un objet JS **Date** qui représente un instant donné de façon indépendante de la plateforme. Les objets Date contiennent un nombre( <small>Number</small> ) qui représente le nombre de millisecondes écoulées depuis le premier janvier 1970.

## Syntaxe

> new Date()
> new Date(year, monthIndex)
> new Date(year, monthIndex, day)
> new Date(year, monthIndex, day, hours)
> new Date(year, monthIndex, day, hours, ...)

<u>Rmq</u>: Les mois commencent à 0

## Méthodes:

Nous pouvons retrouver différentes méthodes.

- **==Date.prototype.getDate()==**
    - La méthode getDate() retourne le jour du mois pour la date spécifiée d'après l'heure locale.

Exemple:

```js
const birthday = new Date('August 19, 1975 23:15:30');
const date1 = birthday.getDate();

console.log(date1);
// retourne 19
```

- **==Date.prototype.getDay()==**
    - La méthode getDay() renvoie le jour de la semaine pour la date spécifiée selon l'heure locale (0 correspond à dimanche).

Exemple:

```js
const birthday = new Date('August 19, 1975 23:15:30');
const day1 = birthday.getDay()

console.log(day1)
// retourne 2 soit mardi
```

* * *

* * *

### Petite parenthèse:

Pour pouvoir afficher le nom complet du jour on pourra utiliser une autre méthode: ==**Intl.DateTimeFormat**==

* * *

( L'objet **Intl** est l'espace de noms pour l'API d'Internationalisation. Elle fournit des outils de comparaison de chaînes de caractère, de formatage de nombre, de dates et de l'heure selon les langues.)

* * *

Exemple:

```js
const date = new Date(Date.UTC(2020, 11, 20, 3, 23, 16, 738));

console.log(new Intl.DateTimeFormat('en-US').format(date))
// retourne "12/20/2020"

console.log(new Intl.DateTimeFormat('en-GB',{dateStyle: 'full', timeStyle:'long'}).format(date));
// 'Sunday, 20 December 2020 at 14:23:16 GMT+11'
```

### Fin de cette petite parenthèse

- **==Date.prototype.getFullYear()==**
    - La méthode getFullYear() renvoie l'année de la date renseignée d'après l'heure locale.

Exemple:

```js
const monnLanding = new Date('July 20, 69 00:20:18');

console.log(moonLanding.getFullYear());
// retourne 1969
```