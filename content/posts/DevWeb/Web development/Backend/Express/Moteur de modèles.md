# Moteur de modèles

Un moteur de modèle, outil qui permet d'inserer des variables et une logique simple dans vos vues

Langage de création de modèles / moteur de visualisation: 
- Pug
- ejs
- hbs
- twig
- vash

## Exemple de moteur de modèle **ejs**

EJS est un langage de création de modèles simple qui permet de générer du balisage HTML 
avec du JS simple.

````html 
<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>
````

Pour en savoir d'avantages [Doc](https://ejs.co/#docs).