# sql

```sql
CREATE TABLE nomdelatable()

ALTER TABLE nomdelatable RENAME / DROP 

DROP TABLE nomdelatable



CREATE TABLE recipes (
    title VARCHAR(150) NOT NULL,
    slug VARCHAR(150) NOT NULL,
        content TEXT,
        duration SMALLINT,
        online BOOLEAN 
    created_at DATETIME
); 

INSERT INTO recipes (title, slug, content, duration, online, created_at) VALUES ('Salade de fruit',  'salede-de-fruit', 'contenu de test', 30, TRUE, 9273982738)
)

-- other exemple
SELECT * FROM table_name;
-- Le symbole * permet d'indiquer que l'on souhaite récupérer toutes les colonnes de notre table.

SELECT col1, col2 FROM table_name;
-- on peut spécifier la liste des champs à récupérer en séparant par une

SELECT name, content, duration FROM recipes WHERE name = 'soupe';
-- WHERE pour rajouter une condition afin de ne récupérer que certaines lignes

UPDATE recipes SET duration = 20, name='SOupe de légumes' WHERE name = 'soupe'
```

## Foreign Key

Une clé étrangère est une colonne ou un groupe de colonnes d'une tables qui fait référence à la clé primaire d'une autre table. Elle établit un lien entre 2 tables, renforçant l'intégrité référentiellen et préservant les relations entre les données associées.

## Aggregate Queries

Les requêtes d'agrégation dans SQL sont utilisées pour effectuer des calculs sur plusieurs lignes de données, renvoyant une valeur récapitulative unique ou des résultats groupés.

Exemple de fonctions d'agrégation:  
COUNT()  
SUM()  
MIN()  
GROUP BY  
....

## Inner Join

Inner Join jointure dans sql est un type de jointure qui renvoie les enregistrements avec des valeurs correspondantes dans les deux tables. Cette opération compare chaque ligne de la première table avec chaque ligne de la seconde table pour trouver toutes les paires de lignes

## Left Join

renvoie toutes les lignes de la table de gauche et les lignes correspondantes de la table de droite.  
S'il y as pas de correspondance dans la table de droite, il renvoie null.

## Right Join

la meme que Left Join, mais inversé.

## Sous requêtes

Une sous requête est un requête intégrée dans une autre requête SQL. Elles sont utilisée pour récupérer des données qui seront utilisée dans la requête principale comme condition pour restreindre davantage les données à récupérer

### Syntaxe

SELECT column_name \[, column_name\]  
FROM table1 \[, table2 \]  
WHERE column_name OPERATOR  
(SELECT column_name \[, column_name\]  
FROM table1 \[, table2 \]  
\[WHERE\])

## CASE

Permet de créer une logique conditionnelle dans une requête, ce qui vous permet d'effectuer différentes actions en fonctions de conditions spécifiques.

### Exemple:

```sql
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;
```

## GROUP BY

Permet d'organiser des données identiques en groupes.

### Exemple:

![1480c4a45a9d39ca51daca5c79b327e6.png](../../../_resources/1480c4a45a9d39ca51daca5c79b327e6.png)

## Having

Permet de filtrer les ensembles de résultats dans une GROUP BY clause. Utilisée pour mentionner des conditions sur les groupes sélectionnés. Comme un WHERE mais sur GROUP BY

## Subqueries

une sous-requête est une requête imbriquée dans une requête principale. Elle peuvent renvoyer des valeurs individuelles...

### Exemple

Order table:  
![54e589588c06ff91313f528b5b4e68ab.png](../../../_resources/54e589588c06ff91313f528b5b4e68ab.png)

Customer table:  
![a739349b04d4033b56809a3167e7fb47.png](../../../_resources/a739349b04d4033b56809a3167e7fb47.png)

![feab6ae1d8e601e696138f8c5765b6c9.png](../../../_resources/feab6ae1d8e601e696138f8c5765b6c9.png)

La sous-requête (partie en parenthèses) est exécutée en premier.

En résumé, cette requête SQL utilise une sous-requête pour récupérer des enregistrements d'une table en fonction d'une condition qui repose sur des informations d'une autre table.

### Nested Subqueries (sous-requêtes imbriquées)

Nested Subqueries sont des sous-requêtes qui contiennent une autre sous-requête.  
La sous-requête la plus interne s'exécute en premier, puis son résultat est utilisé dans la sous requête externe suivant ...

#### Exemple

![261312aaa2b3cbe19daa846577b698c9.png](../../../_resources/261312aaa2b3cbe19daa846577b698c9.png)

### Correlated Subqueries

La requête interne dépend de l'exécution simultanée de la requête externe. (utilise des valeurs de la requête externe). Elle ne peut pas s'exécuter indépendamment de la requête externe car la sous-requête est corrélée à la requête externe.

### Subqueries in the FROM clause

![2110330789ed8c193fa208f204be10b5.png](../../../_resources/2110330789ed8c193fa208f204be10b5.png)

* * *

## Windows Functions

### Difference between windows function & agregation function

une fonction d'agrégation renvoie un seul résultat par groupe de lignes (comme la somme ou la moyenne d'un groupe), une fonction de fenetre renvoie un résultat pour chaque ligne, souvent en relation avec d'autre lignes de la fenetre.

![d3b6891519fcaef960e0f9c018c7d3c8.png](../../../_resources/d3b6891519fcaef960e0f9c018c7d3c8.png)

### Exemple:

![83da8cf00548bb5fc228196dd1d2a7a0.png](../../../_resources/83da8cf00548bb5fc228196dd1d2a7a0.png)

```sql
SELECT 
  SaleID, 
  Salesperson, 
  SaleAmount, 
  SaleDate, 
  SUM(SaleAmount) OVER (ORDER BY SaleDate) AS RunningTotal
FROM Sales;

```

![394a77d2f89ac36bcf5e4b5c0ca23032.png](../../../_resources/394a77d2f89ac36bcf5e4b5c0ca23032.png)

calculer le total cumulé de 'SaleAmout' pour chaque ligne ordonnée par 'SaleDate'

* * *

## Common Table (CTE)

Ensemble de résultats temporaire.  
Les CTE sont définie à l'aide du mot clé WITH et permet de créer une sous-requête nommé et réutilisable dans votre instruction SQL.

### When you would use it

- Simplifiez les requêtes complexes
- Evitez de dupliquer les sous requêtes
- Créez des requêtes récursives

### Syntaxe

```SQL
WITH cte_name (column ...) AS (
        SELECT ....
        FROM....
        WHERE...
)
```

### Exemple

```SQL
WITH Supervisors AS (
    SELECT e.employee_id, e.employee_name, s.supervisor_name
    FROM employees e
    LEFT JOIN employees s ON e.supervisor_id = s.employee_id
)
SELECT employee_id, employee_name, supervisor_name
FROM Supervisors;
```

* * *

## Recursives Queries