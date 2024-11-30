# Express

**Express est un framework d'application web Node.js.**

Un module est une fichier JS qu'on peut importer dans un autre code en utilisant la fonction require() de Node.

Les fonctions de middleware sont des fonctions qui peuvent accéder à l’objet Request (req), l’objet response (res) et à la fonction middleware suivant dans le cycle demande-réponse de l’application. La fonction middleware suivant est couramment désignée par une variable nommée next.
 
 Exécuter tout type de code.
Apporter des modifications aux objets de demande et de réponse.
Terminer le cycle de demande-réponse.
Appeler le middleware suivant dans la pile.
 
 
 ````
 var express = require('express');
var router = express.Router();

// middleware that is specific to this router
router.use(function timeLog(req, res, next) {
  console.log('Time: ', Date.now());
  next();
});
// define the home page route
router.get('/', function(req, res) {
  res.send('Birds home page');
});
// define the about route
router.get('/about', function(req, res) {
  res.send('About birds');
});

module.exports = router;

var birds = require('./birds');
...
app.use('/birds', birds);
````




chercher signification cdn, reregarder video promiser, regarder video like yt, continuer le cours 


# Express


### Middleware / intergiciels

simple fonction JS  qu'Express appellera pour entre le moment ou il recoit une requete 
réseau et le moment ou il declenche une réponse.
prends 3 arguments: req et res qui sont des objets et next*1 = fonction
Exemple
````javascript
function(req, res, next) {
  // do stuff!
}

// Exemple:

const myLogger = function(req, res, next) {
  console.log("Request IP: " + req.ip);
  console.log("Request Method: " + req.method);
  console.log("Request date: " + new Date());

  next(); // THIS IS IMPORTANT!
}

app.use(myLogger)
````


*1
Si vous écrivez ou utilisez un middleware qui ne renvoie pas de réponse au client de l'utilisateur, vous devez appeler la nextfonction à la fin de votre fonction middleware. La fonction suivante indique simplement à express de passer au middleware suivant dans la pile, mais si vous oubliez de l'appeler, votre application se mettra en pause et rien ne se passera !
app.use permet de charger la fonction middleware dans Express afin qu'il sache l'utiliser.


moteur de feuille de style css:
- less
- sass
- compass 
- stylus



module ou fichier contiennent du code



````javascript
const createError = require("http-errors");
const express = require("express");
const path = require("path");
const cookieParser = require("cookie-parser");
const logger = require("morgan");
````
