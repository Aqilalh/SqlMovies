# SqlMovies


//former table
+----------+--------------+------+-----+---------+----------------+
| Field    | Type         | Null | Key | Default | Extra          |
+----------+--------------+------+-----+---------+----------------+
| id       | int unsigned | NO   | PRI | NULL    | auto_increment |
| title    | varchar(20)  | NO   |     |         |                |
| genre    | varchar(20)  | NO   |     |         |                |
| duration | int unsigned | NO   |     | 0       |                |
+----------+--------------+------+-----+---------+----------------+

//adding data into the table
mysql> insert into movies(id, title, genre, duration)
    -> VALUES (1, 'Metropolis', 'Sci-Fi', 153);
Query OK, 1 row affected (0.03 sec)

mysql> insert into movies(id, title, genre, duration)
    -> VALUES (2, 'Nosferatu', 'Horror', 94);
Query OK, 1 row affected (0.00 sec)

mysql> insert into movies(id, title, genre, duration)
    -> VALUES (3, 'The kid', 'Comedy', 68);
Query OK, 1 row affected (0.00 sec)

mysql> insert into movies(id, title, genre, duration)
    -> VALUES (4, 'The Gold Rush', 'Adevnture', 95);
Query OK, 1 row affected (0.01 sec)

//after adding data
mysql> select * from movies

+----+---------------+-----------+----------+
| id | title         | genre     | duration |
+----+---------------+-----------+----------+
|  1 | Metropolis    | Sci-Fi    |      153 |
|  2 | Nosferatu     | Horror    |       94 |
|  3 | The kid       | Comedy    |       68 |
|  4 | The Gold Rush | Adevnture |       95 |
+----+---------------+-----------+----------+

//Updating data
mysql> update movies
    -> SET genre = 'Romance'
    -> WHERE id = 4;
Query OK, 1 row affected (0.02 sec)
Rows matched: 1  Changed: 1  Warnings: 0
+----+---------------+---------+----------+
| id | title         | genre   | duration |
+----+---------------+---------+----------+
|  1 | Metropolis    | Sci-Fi  |      153 |
|  2 | Nosferatu     | Horror  |       94 |
|  3 | The kid       | Comedy  |       68 |
|  4 | The Gold Rush | Romance |       95 |
+----+---------------+---------+----------+
// add a column and adding data inside
mysql> ALTER TABLE movies
    -> ADD COLUMN ratings int;
Query OK, 0 rows affected (0.13 sec)


mysql> UPDATE movies
    -> SET ratings = 8
    -> WHERE title='The kid';
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> UPDATE movies
    -> SET ratings = 5
    -> WHERE title='The Gold Rush';
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> UPDATE movies
    -> SET ratings = 6
    -> WHERE title='Nosferatu';
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> UPDATE movies
    -> SET ratings = 9
    -> WHERE title='Metropolis';
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

