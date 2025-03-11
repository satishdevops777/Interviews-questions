1. MySQL (Relational Database)
1. What is MySQL, and why is it used?
Answer:
MySQL is an open-source relational database management system (RDBMS) used for structured data storage with SQL-based queries.

2. What is the difference between MySQL and NoSQL databases?
Feature	MySQL (SQL)	NoSQL
Data Structure	Relational (Tables, Rows)	Document, Key-Value, Graph, Column-based
Schema	Fixed Schema	Schema-less (Flexible)
Query Language	SQL	NoSQL APIs (MongoDB Query, DynamoDB, etc.)
Transactions	ACID-compliant	BASE (Eventually Consistent)
3. What is the difference between INNER JOIN, LEFT JOIN, and RIGHT JOIN?
Answer:

INNER JOIN: Returns matching rows from both tables.
LEFT JOIN: Returns all rows from the left table and matching rows from the right.
RIGHT JOIN: Returns all rows from the right table and matching rows from the left.
Example:

sql
Copy
Edit
SELECT orders.id, customers.name 
FROM orders 
INNER JOIN customers ON orders.customer_id = customers.id;
4. How do you optimize a slow MySQL query?
Answer:

Use Indexes (CREATE INDEX idx_name ON table(column);)
**Avoid SELECT *** (Fetch only required columns).
Optimize JOINS (Use proper indexing).
Use EXPLAIN ANALYZE to check query execution plan.
5. What are MySQL Transactions, and how do you use them?
Answer:
Transactions ensure atomicity, consistency, isolation, and durability (ACID).

sql
Copy
Edit
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE user_id = 1;
UPDATE accounts SET balance = balance + 100 WHERE user_id = 2;
COMMIT;
6. What is the difference between MyISAM and InnoDB storage engines?
Feature	MyISAM	InnoDB
Transactions	No	Yes
Foreign Keys	No	Yes
Row-level Locking	No (Table Lock)	Yes
Performance	Faster for reads	Better for writes
7. How do you perform database backup in MySQL?
Answer:
Using mysqldump command:

bash
Copy
Edit
mysqldump -u root -p database_name > backup.sql
Restore backup:

bash
Copy
Edit
mysql -u root -p database_name < backup.sql
8. What is replication in MySQL?
Answer:
Replication allows one database server (Master) to sync data to another (Slave) for backup, load balancing, or high availability.

9. What are stored procedures in MySQL?
Answer:
Stored procedures are predefined SQL scripts that can be executed with a single call.

sql
Copy
Edit
DELIMITER //
CREATE PROCEDURE GetCustomers()
BEGIN
   SELECT * FROM customers;
END //
DELIMITER ;
10. What is a foreign key constraint in MySQL?
Answer:
A foreign key enforces referential integrity between tables.

sql
Copy
Edit
ALTER TABLE orders ADD FOREIGN KEY (customer_id) REFERENCES customers(id);
2. NoSQL (MongoDB, DynamoDB, etc.)
1. What is NoSQL, and why is it used?
Answer:
NoSQL databases store unstructured or semi-structured data and are designed for scalability, flexibility, and high availability.

2. What are the different types of NoSQL databases?
Answer:

Document-based: MongoDB
Key-Value: Redis, DynamoDB
Column-based: Apache Cassandra
Graph-based: Neo4j
3. How does MongoDB store data?
Answer:
MongoDB stores data as JSON-like documents (BSON format) in collections instead of tables.

Example document:

json
Copy
Edit
{
  "_id": "12345",
  "name": "John Doe",
  "email": "john@example.com",
  "orders": [1001, 1002]
}
4. What is the difference between SQL and MongoDB queries?
SQL (MySQL)	MongoDB (NoSQL)
SELECT * FROM users WHERE age > 30;	db.users.find({ age: { $gt: 30 } })
INSERT INTO users(name, age) VALUES('Alice', 25);	db.users.insertOne({ name: "Alice", age: 25 })
UPDATE users SET age=26 WHERE name='Alice';	db.users.updateOne({ name: "Alice" }, { $set: { age: 26 } })
5. How does indexing work in MongoDB?
Answer:
Indexes improve query performance.

bash
Copy
Edit
db.users.createIndex({ email: 1 })  # Ascending index on email field
6. What is sharding in MongoDB?
Answer:
Sharding splits large datasets across multiple nodes to improve scalability and performance.

7. How does MongoDB handle replication?
Answer:
MongoDB uses Replica Sets (Primary-Secondary nodes) for high availability.

8. What is Amazon DynamoDB?
Answer:
DynamoDB is a fully managed key-value NoSQL database by AWS with automatic scaling and low-latency performance.

9. How does DynamoDB differ from MongoDB?
Feature	MongoDB	DynamoDB
Hosting	Self-hosted / Cloud	AWS-managed
Schema	Schema-less	Schema-less
Scaling	Horizontal (Sharding)	Auto-scaling
Query Language	MongoDB Query API	DynamoDB Query API
10. How do you perform a query in DynamoDB?
Answer:

python
Copy
Edit
import boto3
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table('Users')
response = table.get_item(Key={'user_id': '1234'})
print(response['Item'])
