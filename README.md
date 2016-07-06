<!-- How many users are there?
SELECT COUNT(*) FROM users

What are the 5 most expensive items?
SELECT price FROM items ORDER BY price DESC LIMIT 5;

What's the cheapest book? (Does that change for "category is exactly 'book'"
 versus "category contains 'book'"?)
SELECT title, category, price FROM ITEMS ORDER BY price LIMIT 1;

Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?
 SELECT * FROM addresses WHERE zip LIKE '150__';

Correct Virginie Mitchell's address to "New York, NY, 10108".
SELECT id FROM addresses first_name = 'Virginie'
39

SELECT * FROM addresses WHERE id LIKE '39';

UPDATE addresses SET city = 'New York', state = 'NY', zip = '10108' WHERE id = 39;

How much would it cost to buy one of each tool?
SELECT SUM(price) FROM items;
467488

How many total items did we sell?
SELECT * FROM orders;

SELECT item_id FROM orders;

SELECT SUM(item_id) FROM orders;
19334

How much was spent on books?
SELECT * FROM items WHERE category LIKE 'book_';
id|title|category|description|price
4|Fantastic Steel Chair|Books|Advanced attitude-oriented encryption|9246
21|Fantastic Rubber Shoes|Books|Reverse-engineered modular hierarchy|8904
76|Ergonomic Granite Chair|Books|De-engineered bi-directional portal|1496
98|Practical Plastic Hat|Books|Implemented non-volatile model|3056

SELECT SUM(price) FROM items WHERE category IN ('Books');
SUM(price)
22702

Simulate buying an item by inserting a User for yourself and an Order for that User. -->

sqlite> INSERT INTO users VALUES (51, "Max", "Anam", "maxanana@lite.nik");

sqlite> SELECT * FROM users;

51|Max|Anam|maxanana@lite.nik

sqlite> SELECT * FROM items JOIN orders ON orders.item_id = items.id WHERE orders.user_id = 51;
