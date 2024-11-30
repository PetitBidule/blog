# Flutter

 ### Interface entre le code et le dispositif physique

![cycle de vie d'un widget avec état](https://www.flutteris.com/_image_/internals_archi_overview.png)

Lorsque nous écrivons une application Flutter, en utilisant Dart, nous restons au niveau du Flutter Framework (partie en vert).

Le Framework Flutter intéragit avec Le Flutter Engine (partie en bleu) ([pour en savoir plus sur Flutter Engine](https://github.com/flutter/engine?tab=readme-ov-file)) , via une couche d'abstraction, appelée Window. Cette couche d'abstraction expose une série d'API pour communiquer, indirectement avec l'appareil. 

C'est également via cette couche d'abstraction que le moteur Flutter notifie le cadre Flutter lorsque, entre autres:
- Un évènement intéressant se produit au niveau de l'appareil (changement d'orientation, changement de paramètres, problèmes de mémoire, état d'exécution de l'application...)

### Flutter Framework est piloté par le moteur de rendu de cadre Flutter Engine.

Aucun code du Framework Flutter n'est exécuté sans avoir été déclenché par le rendu du moteur Flutter.

Ceci explique le processus de mise a jour du rendu dans le moteur Flutter.
![cycle de vie d'un widget avec état](https://www.flutteris.com/_image_/internals_flow.gif)
Comme dit un peu plus haut, des évènement externes tels que des gestes utilisateurs , des réponses HTTP peuvent déclencher des taches nécessitant une mise a jour du rendu.

- Lorsqu'une mise a jour du rendu est nécessaire, un message est envoyé au moteur Flutter pour le notifier. C'est ce qu'on appelle le "**Schedule Frame**".
- Ensuite lorsque le moteur Flutter est prêt à effectuer le rendu, il émet une requête **Begin Frame**.
- Cette dernière est intercéptée par le Framework. Des taches liées aux "Tickers" (exemple: les animations.) sont exécutées.
- Ces tâches peuvent éventuellement générer de nouvelles requêtes pour des rendus ultérieurs. Par exemple, une animation incomplète pourrait demander un autre "Begin Frame" ultérieurement.
- Le moteur Flutter émet ensuite une requête **Draw Frame**.
- Cette requête "Draw Frame" est interceptée par le framework Flutter. Il effectue des tâches liées à la mise à jour de la disposition en termes de structure et de taille.
- Une fois ces tâches terminées, le framework procède aux tâches liées à la mise à jour de l'apparence visuelle des widgets (comme l'opacité, les ombres, les couleurs...).
- S'il y a quelque chose à dessiner à l'écran, le framework envoie la nouvelle scène à rendre au moteur Flutter.
- Enfin, le framework Flutter exécute toutes les tâches à effectuer après le rendu complet (appelées "PostFrame callbacks") et d'autres tâches non liées au rendu.
- Ce flux de travail est répétée, créant ainsi un cycle continu de mise à jour.

## RenderView et RenderObject

Tout finit par devenir une série de pixels à afficher sur l'écran d'un iphone ou d'une tablette etc, le Framework Flutter convertit les Widgets que nous utilisons pour développer nos applications en ==parties visuelles== qui seront rendues sur l'écran.

Ces ==parties visuelles== qui sont rendues à l'écran correspondent à des objets, appelés ==RenderObjects== qui sont utilisés pour:

- Définir une zone de l'écran en termes de dimensions, de position, de géométrie mais aussi en termes de "contenu de rendu".
- Identifier les zones de l'écran potentiellement impactées par les gestes (appuie sur un bouton par exemple).
- L'ensemble des RenderObject forme un arbre, appelée ==Render Tree==. Au sommet de cet arbre, on trouve un RenderView == représente la surface de sortie totale du Render Tree.

![alt text](https://www.flutteris.com/_image_/internals_renderView.png)

### Widget: 
Dans le contexte de Flutter, le terme "widget" fait référence à tout élément d'interface utilisateur, qu'il s'agisse d'un bouton, d'un champ de texte, d'une image, etc. Chaque composant de l'interface utilisateur que vous construisez est un widget.

StatelessWidget = widget sans état ne changera pas  
StatefulWidgets = widget avec état peut etre changé au fil du temps.
Cycle de vie d'un widget avec état:

![cycle de vie d'un widget avec état](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*Y9GSycXudnvPG41EZA1cXQ.png)

- initState(): Cette méthode est appelée une fois lorsque l'objet est inséré dans l'arborescence.
- dispose(): Appelée lorsqeu cet objet est supprimé définitivement de l'arborescence.
- didChangeDependencies(): Appelée lorsque cet objet State change.
- setState(): notifie au framework que l'état de cet objet a changé et déclenche la consrtuction de cet objet State et met a jour l'interface utilisateur. 


# différence entre final et const et late:

 ## final:

- une variable avec le final mot clé sera initialisée au moment de l'éxecution et ne pourra etre affectée qu'une seule fois.
- on peut le définir dans une classe et une fonction.

## const:

- const est initialisée au moment de la compilation et est déjà affectée au moment de l'exécution.
- on ne peut pas le définir à l'intérieur d'une classe, mais on peut dans une fonction.

## late

late est utilisée pour déclarer des variables qui seront initialisées plus tard 

Quand l'utiliser?  
Final: si on ne sait pas quelle sera la valeur au moment de la compilation  
Const: si le valeur ne sera pas modifiée lors de l'exécution: Exemple: lorsqu'on délcare une phrase qui reste toujours la meme.

---
## @override:  
Souligne simplement que la fonction est également définie dans une classe ancêtre, mais qu'elle est en cours de redéfinition pour faire autre chose dans la classe actuelle. Il est également utilisé pour annoter l'implémentation d'une méthode abstraite. Son utilisation est facultative mais recommandée car elle améliore la lisibilité.

---
## bool? utilisation:
L'utilisation d'un point d'un point d'interrogation après un type comme le bool, int etc, indique que cette variable peut avoir une valeur null.

---
## underscore variable:
L'underscore devant le nom d'une variable est une convention pour indiquer que cette variable est privée à la portée de son fichier ou de sa classe.

---
## VoidCallback
Type de fonction qui ne prend aucun argument et ne retourne rien.
Par exemple un voidCallback pourrait etre utilisée pour définir ce qui doit se passer lorsque l'utilisateur appuie sur un boutton. 

---
## const et enum
const est utilisé pour créer des objets immuables
enum permet de regrouper plusieurs variable immuables, en gro plusieur const.
Exemple:
Au lieu d'écrice ceci:
````dart
const notStarted = 'Not Started',
const inProgress = 'In Progress',
const completed = 'Completed',
const onHold = 'On Hold',
````
Nous pouvons avoir ceci:
````dart
enum Status {notStarted, inProgress, completed, onHold}
````


---
## différence entre remove et removeAt
on utilise removeAt quand nous ne connaisons pas la valeur, nous allons donc nous baser sur l'index.
removeAt prend en paramèter l'index de la liste.
à l'inverse nous allons utiliser remove lorsqu'on connait l'élément de la liste. 
il prend en paramètre l'élément et le supprime 
````dart
List<int> maListe = [1, 2, 3, 4, 5, 3];
maListe.remove(3); // Supprime la première occurrence du 3 dans la liste
````

## dispose() method 
la method dispose permet de gérer les ressources, de libérer de la mémoire et d'éviter les fuites de mémoire