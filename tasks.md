
# SQL Problem Sets (Ongelmajoukot)

## Yhteen tauluun kohdistuvien kyselyiden harjoitukset:

### Tehtävä 1:

SELECT * from goal;

![Task1.png](Tasks/Task1.png)

### Tehtävä 2:

SELECT name, type FROM airport WHERE iso_country = "FI";

![Task2.png](Tasks/Task2.png)

### Tehtävä 3:

SELECT name FROM airport WHERE iso_country = "FI";

![Task3.png!](Tasks/Task3.png)

### Tehtävä 4:

SELECT name, type FROM airport WHERE iso_country = 'FI' ORDER BY type ASC, name ASC;

![Task4.png](Tasks/Task4.png)

### Tehtävä 5:

SELECT name FROM country WHERE name LIKE 'F%';

![Task5.png](Tasks/Task5.png)

### Tehtävä 6:

SELECT name FROM country WHERE name LIKE '%F%';

![Task6.png](Tasks/Task6.png)

### Tehtävä 7:

SELECT location FROM game WHERE screen_name = 'Vesa';

![Task7.png](Tasks/Task7.png)

### Tehtävä 8:

SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';

![Task8.png](Tasks/Task8.png)

### Tehtävä 9:

SELECT DISTINCT co2_budget FROM game;

![Task9.png](Tasks/Task9.png)

## Where-osan liitosehto harjoitukset:

### Tehtävä 1:

SELECT country.name AS "country name", airport.name AS "airport name" FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE country.name = 'Iceland';

![Part2Task1.png](Tasks/Part2Task1.png)


### Tehtävä 2:

SELECT name AS "airport name" FROM airport WHERE iso_country = 'FR' AND type = 'large_airport';

![Part2Task2.png](Tasks/Part2Task2.png)

### Tehtävä 3:

SELECT country.name AS country_name, airport.name AS airport_name FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE airport.continent = 'AN';

![Part2Task3.png](Tasks/Part2Task3.png)

### Tehtävä 4:

SELECT elevation_ft FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Heini';

![Part2Task4.png](Tasks/Part2Task4.png)

### Tehtävä 5:

SELECT elevation_ft * 0.3048 AS elevation_m FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Heini';

![Part2Task5.png](Tasks/Part2Task5.png)

### Tehtävä 6:

SELECT airport.name FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Ilkka';

![Part2Task6.png](Tasks/Part2Task6.png)

### Tehtävä 7:

SELECT DISTINCT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Ilkka';

![Part2Task7.png](Tasks/Part2Task7.png)

### Tehtävä 8:

SELECT goal.name FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id WHERE game.screen_name = 'Heini';

![Part2Task8.png](Tasks/Part2Task8.png)

### Tehtävä 9:

SELECT DISTINCT airport.name FROM airport JOIN goal_reached ON airport.ident = (SELECT location FROM game WHERE screen_name = 'Ilkka') JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'clouds';

![Part2Task9.png](Tasks/Part2Task9.png)

### Tehtävä 10:

SELECT DISTINCT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country JOIN goal_reached ON airport.ident = (SELECT location FROM game WHERE screen_name = 'Ilkka') JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'clouds';

![Part2Task10.png](Tasks/Part2Task10.png)

## Join harjoitukset:

### Tehtävä 1:

SELECT country.name AS "country name", airport.name AS "airport name" FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name = 'Finland' AND airport.scheduled_service = 'yes';

![Part3Task1.png](Tasks/Part3Task1.png)

### Tehtävä 2:

SELECT game.screen_name, airport.name FROM game JOIN airport ON game.location = airport.ident;

![Part3Task2.png](Tasks/Part3Task2.png)

### Tehtävä 3:

SELECT game.screen_name, country.name FROM game JOIN airport ON game.location = airport.ident JOIN country ON airport.iso_country = country.iso_country;

![Part3Task3.png](Tasks/Part3Task3.png)

### Tehtävä 4:

SELECT airport.name, game.screen_name FROM airport LEFT JOIN game ON airport.ident = game.location WHERE airport.name LIKE '%Hels%';

![Part3Task4.png](Tasks/Part3Task4.png)

### Tehtävä 5:

SELECT goal.name AS "goal name", game.screen_name FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id;

![Part3Task5.png](Tasks/Part3Task5.png)

## Sisäkysely harjoitukset:

### Tehtävä 1:

SELECT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE airport.name LIKE 'Satsuma%';

![Part4Task1.png](Tasks/Part4Task1.png)

### Tehtävä 2:

SELECT airport.name FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name = 'Monaco';

![Part4Task2.png](Tasks/Part4Task2.png)

### Tehtävä 3:

SELECT game.screen_name FROM game JOIN goal_reached ON game.id = goal_reached.game_id JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'CLOUDS';

![Part4Task3.png](Tasks/Part4Task3.png)

### Tehtävä 4:

SELECT country.name FROM country WHERE country.iso_country NOT IN (SELECT DISTINCT airport.iso_country FROM airport);

![Part4Task4.png](Tasks/Part4Task4.png)

### Tehtävä 5:

SELECT goal.name FROM goal WHERE goal.id NOT IN (SELECT goal.id FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id WHERE game.screen_name = 'Heini');

![Part4Task5.png](Tasks/Part4Task5.png)




