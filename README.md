# 01---Discuter-en-SQL
--------recupuration de la db-------------
-- SELECT * FROM tutorial.dc_bikeshare_q1_2012
------Selection bike number et duration
-- SELECT bike_number,
--       SUM(duration_seconds)/3600 AS duration_hours
-- FROM tutorial.dc_bikeshare_q1_2012
-- GROUP BY bike_number
-- ORDER BY duration_hours DESC;
-----Étape 1: Sélectionner bike_number et duration_seconds
SELECT
  bike_number,
  duration_seconds
FROM
  tutorial.dc_bikeshare_q1_2012;

-----Étape 2: Organiser les Résultats par duration_seconds
SELECT
  bike_number,
  duration_seconds
FROM
  tutorial.dc_bikeshare_q1_2012
ORDER BY
  duration_seconds DESC;

----Étape 3: Limiter les Résultats à 300
SELECT
  bike_number,
  duration_seconds
FROM
  tutorial.dc_bikeshare_q1_2012
ORDER BY
  duration_seconds DESC
LIMIT
  300;

---Étape 4: Convertir duration_seconds en Heures et Renommer la Colonne
SELECT
  bike_number,
  duration_seconds / 3600 AS duration_hours
FROM
  tutorial.dc_bikeshare_q1_2012
ORDER BY
  duration_seconds DESC
LIMIT
  300;

-- Cette requête finale répondra aux critères de validation :
-- Elle liste les 300 vélos ayant le plus d'heures d'utilisation.
-- Les colonnes sont intitulées bike_number et duration_hours.
-- Les vélos les plus utilisés sont listés en premier.
-- Le temps d'utilisation maximal est affiché en heures.
------Étape 5: Grouper par bike_number et Faire la Somme des duration_seconds
SELECT
  bike_number,
  SUM(duration_seconds) / 3600 AS duration_hours
FROM
  tutorial.dc_bikeshare_q1_2012
GROUP BY
  bike_number
ORDER BY
  duration_hours DESC
LIMIT
  300;
