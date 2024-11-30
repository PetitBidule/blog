# Cookie

les cookies = petits élément de donnés stockés sur le pc.

Les cookies sont enregistrés lorsque vous recevez un en tête "Set-cookie" d'un serveur web. 
Ensuite, à chaque nouvelle demande que tu fais, tu renvoie les données du cookie au serveur web. 
Etant donné que http est sans état (ne garde donc pas la trace de des demandes précédentes), les cookies sont un bon moyen pour être utilisés pour rappeler au serveur web qui tu es.

![38ab18d50d6599c3249e640c5b7c354e.png](../_resources/38ab18d50d6599c3249e640c5b7c354e.png)

Par exemple, si on crée une application de messagerie web, vous pouvez attribuer à chaque utilisateur après la connexion un cookie contenant son nom d'utilisateur. Lors des requêtes ultérieures, le navigateur enverra toujours le nom d'utilisateur dans le cookie afin que l'application web sache quel utilisateur se connecte. Ce serait une très mauvaise idée du point de vue sécurité, car comme les cookies sont stockés sur le navigateur de l'utilisateur, donc si l'utilisateur altère le cookie et modifie le nom d'utilisateur, il pourrait usurper l'identité d'une autre personne. 

Solution: JWT (Json Web Tokens)

JSON = Javascipt Object Notation est un format d'échange de fichiers et de données standard ouvert qui utilise du texte lisible par l'homme pour stocker et transmettre des objets de données constitués de paires et de tableaux attribut-valeur.