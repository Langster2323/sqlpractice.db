<!-- How many users are there?
SELECT COUNT(*) FROM users;

What are the 5 most expensive items?
SELECT price FROM items ORDER BY price DESC LIMIT 5;

What's the cheapest book? (Does that change for "category is exactly 'book'"
 versus "category contains 'book'"?)
SELECT title, category, price FROM ITEMS ORDER BY price LIMIT 1;

Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?
 SELECT first_name FROM addresses
 WHERE city = Willmouth
 AND
 state = WY;

Correct Virginie Mitchell's address to "New York, NY, 10108".
SELECT id FROM addresses WHERE first_name = 'Virginie'
39

SELECT * FROM addresses WHERE id LIKE '39';

UPDATE addresses SET city = 'New York', state = 'NY', zip = '10108' WHERE id = 39;

How much would it cost to buy one of each tool?
SELECT SUM(price) FROM items WHERE category = "Tools";
7383

How many total items did we sell?


SELECT SUM(quantity) FROM orders;
2125

How much was spent on books?

SELECT SUM(price * quantity) FROM items INNER JOIN orders ON items.id = orders.item_id WHERE category = "books";
Simulate buying an item by inserting a User for yourself and an Order for that User. -->

<!-- sqlite> INSERT INTO users VALUES (51, "Max", "Anam", "maxanana@lite.nik");

sqlite> SELECT * FROM users;

51|Max|Anam|maxanana@lite.nik
INSERT INTO orders VALUES (51, 23, 99, current_timestamp);
SELECT * FROM items WHERE id = 23; -->

SELECT title, SUM(quantity) FROM items JOIN orders ON orders.item_id = items.id GROUP BY items.id ORDER BY SUM(quantity) DESC LIMIT 5;

SELECT title, SUM(price * quantity) FROM items HOIN orders ON orders.item_id = items.id GROUP BY items.id ORDER BY SUM(price * quantity) DESC LIMIT 5;

SELECT first_name, last_name, SUM(price * quantity) FROM users JOIN orders ON ORDERS.USER_ID = USERS.ID join ITEMS ON orders.item_id = items.id GOUP BY users.id ORDER BY SUM(price * quantity) DESC LIMIT 5;

What were the top 3 highest grossing categories?
