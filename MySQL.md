### Задание MySQL:

7) В подключенном MySQL репозитории создать базу данных “Друзья
человека”.
> mysql -u root  
CREATE database human_friends;  
USE human_friends;

8) Создать таблицы с иерархией из диаграммы в БД.

> CREATE TABLE animals (Id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(20), command VARCHAR(20), type_id INT NOT NULL);  
CREATE TABLE category (Id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(20));  
CREATE TABLE type (Id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(20), cat_id INT NOT NULL);  
ALTER TABLE type ADD FOREIGN KEY (cat_id) REFERENCES category(id);  
ALTER TABLE animals ADD FOREIGN KEY (type_id) REFERENCES type(id);  
ALTER TABLE animals ADD COLUMN birthdate DATE AFTER command;  

9) Заполнить низкоуровневые таблицы именами(животных), командами
которые они выполняют и датами рождения.
> INSERT INTO category(name) VALUES ('pets'), ('pack_animals');  
INSERT INTO type(name, cat_id) VALUES ('dog', 1),('cat', 1),('hamster', 1),('horse', 2),('camel', 2),('donkey', 2);  
INSERT INTO animals(name, command, type_id) VALUES ('Bill', 'run', 1),('Murka','eat', 2),('Venya', 'sleep', 3),('Flash', 'rest', 4),('Sahara','drink', 5),('Sunny', 'drink', 5);  
UPDATE animals SET birthdate='2020-01-01'  WHERE name='Bill';
UPDATE animals SET birthdate='2015-02-02' WHERE name='Murka';  
UPDATE animals SET birthdate='2021-03-01' WHERE name='Venya';  
UPDATE animals SET birthdate='2010-10-11' WHERE name='Flash';  
UPDATE animals SET birthdate='2020-12-12' WHERE name='Sahara';  
UPDATE animals SET birthdate='2019-04-05' WHERE name='Sunny';  

10) Удалив из таблицы верблюдов, т.к. верблюдов решили перевезти в другой
питомник на зимовку. Объединить таблицы лошади, и ослы в одну таблицу.
> DELETE FROM animals WHERE type_id=5;

11) Создать новую таблицу “молодые животные” в которую попадут все
животные старше 1 года, но младше 3 лет и в отдельном столбце с точностью
до месяца подсчитать возраст животных в новой таблице.
>CREATE TABLE young_animals SELECT a.id, a.name, a.command, a.birthdate, YEAR(CURDATE())-YEAR(birthdate) AS age 
    FROM animals a WHERE YEAR(CURDATE())-YEAR(birthdate) BETWEEN 1 and 3;

12) Объединить все таблицы в одну, при этом сохраняя поля, указывающие на
прошлую принадлежность к старым таблицам.

> CREATE TABLE summary SELECT a.id, a.name, a.command, a.birthdate, t.name AS 'animals_type', c.name AS 'animals_category'
    FROM animals AS a JOIN type AS t ON a.type_id=t.id LEFT
    JOIN category AS c ON t.cat_id=c.id;