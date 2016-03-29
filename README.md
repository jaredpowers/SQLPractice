1. How many users are there? There are 50 users
select * from users

2. What are the 5 most expensive items?
In descending order:
Small Cotton Gloves
Small Wooden Computer
Awesome Granite Pants
Sleek Wooden Hat
Ergonomic Steel Car

select * from items order by price desc limit(5);

3. What's the cheapest book? (Does that change for "category is exactly 'book'" versus "category contains 'book'"?)
Books|De-engineered bi-directional portal|1496

SELECT * FROM items WHERE category LIKE "%Books%" ORDER BY price asc LIMIT(1);

4. Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?
Corrine Little lives at 6439 Zetta Hills and she has another home at 54369 Wolff Forges, Lake Bryon CA 31587

select * from addresses where street like '%6439%';

5. Correct Virginie Mitchell's address to "New York, NY, 10108".
UPDATE addresses SET city = 'New York' WHERE street = '12263 Jake Crossing';
UPDATE addresses SET zip = '10108' WHERE street = '12263 Jake Crossing';
UPDATE addresses SET state = 'NY' WHERE street = '12263 Jake Crossing';

6. How much would it cost to buy one of each tool?
7383 pennies
SELECT sum(price) FROM items WHERE category = "Tools";

7. How many total items did we sell?
2125
SELECT sum(quantity) FROM orders;

8. How much was spent on books?
22702
SELECT sum(price) FROM items WHERE category = "Books";

9. Simulate buying an item by inserting a User for yourself and an Order for that User.
INSERT INTO users VALUES (51, "Jared", "Powers", "jarpow44@gmail.com");
INSERT INTO orders VALUES (447, "51", "1", "1", CURRENT_TIMESTAMP);
