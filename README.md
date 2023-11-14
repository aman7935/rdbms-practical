# 1.comparative study of various database management systems
Here's a list of various types of Database Management Systems (DBMS) 

markdown
## Database Management Systems

### Relational Database Management Systems (RDBMS)

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- SQLite

### NoSQL Database Management Systems

- MongoDB (document-oriented)
- Cassandra (wide-column store)
- Redis (key-value store)
- Neo4j (graph database)
- CouchDB (document-oriented)

### Object-Oriented Database Management Systems (OODBMS)

- db4o
- ObjectDB

### NewSQL Database Management Systems

- Google Spanner
- CockroachDB
- NuoDB

### In-Memory Database Management Systems

- Redis (can also be classified as NoSQL)
- Memcached

### Columnar Database Management Systems

- Apache HBase
- Amazon Redshift

### Time-Series Database Management Systems

- InfluxDB
- OpenTSDB

### Graph Database Management Systems

- Neo4j
- Amazon Neptune

# 2. Data Definition Language (DDL), Data Manipulation Language (DML), and Data Control 
Language (DCL)
| Data Definition Language (DDL) | Description                                               | Example                                      |
|-------------------------------|-----------------------------------------------------------|----------------------------------------------|
| CREATE                        | Defines new database objects such as tables, indexes, etc. | `CREATE TABLE users (id INT PRIMARY KEY, username VARCHAR(50) NOT NULL, email VARCHAR(100) UNIQUE);` |
| ALTER                         | Modifies the structure of an existing database object.    | `ALTER TABLE users ADD COLUMN birthdate DATE;` |
| DROP                          | Deletes a database object (e.g., table, index).           | `DROP TABLE users;`                          |

| Data Manipulation Language (DML) | Description                                   | Example                                        |
|----------------------------------|-----------------------------------------------|------------------------------------------------|
| SELECT                           | Retrieves data from one or more tables.      | `SELECT * FROM users WHERE age > 21;`           |
| INSERT                           | Adds new records into a table.               | `INSERT INTO users (username, email) VALUES ('JohnDoe', 'john@example.com');` |
| UPDATE                           | Modifies existing records in a table.        | `UPDATE users SET age = 25 WHERE username = 'JohnDoe';` |
| DELETE                           | Removes records from a table.                | `DELETE FROM users WHERE username = 'JohnDoe';` |

| Data Control Language (DCL) | Description                                | Example                                           |
|-----------------------------|--------------------------------------------|---------------------------------------------------|
| GRANT                       | Provides specific privileges to users.     | `GRANT SELECT, INSERT ON users TO employee_role;` |
| REVOKE                      | Withdraws previously granted permissions. | `REVOKE INSERT ON users FROM employee_role;`      |
| DENY                        | Explicitly denies certain permissions.      | `DENY DELETE ON users TO temporary_user;`         |
# 3. How to apply Constraints at various levels.
## Constraints in Database Design

### Table-Level Constraints

### 1. primary key
A primary key is a column or set of columns in a relational database table that uniquely identifies each row in the table. 

example :-

creating table with primary key

![Screenshot 2023-11-14 135251](https://github.com/aman7935/rdbms-practical/assets/146933698/835cc553-2f68-4753-9c70-538e46bc7c04)

inserting values in table :-

![Screenshot 2023-11-14 141017](https://github.com/aman7935/rdbms-practical/assets/146933698/1b95e0eb-1bf3-4cd6-b40b-10772dd9ad30)

OUtput :-

![Screenshot 2023-11-14 141213](https://github.com/aman7935/rdbms-practical/assets/146933698/43d9b9bb-20a7-4018-bf60-6f55799e1f3f)

### 2. foreign key

creating table with primary key

![Screenshot 2023-11-14 135251](https://github.com/aman7935/rdbms-practical/assets/146933698/835cc553-2f68-4753-9c70-538e46bc7c04)

foreign key referencing from first table :-

![Screenshot 2023-11-14 144039](https://github.com/aman7935/rdbms-practical/assets/146933698/6947d049-57bf-49c3-9898-6b7970b5e4bb)

Inserting in 2nd table with the name of courses :-

![Screenshot 2023-11-14 144309](https://github.com/aman7935/rdbms-practical/assets/146933698/e21f750f-5d74-4a4a-abe5-4093af2e57d7)

OUtput after the execution :-

![Screenshot 2023-11-14 144446](https://github.com/aman7935/rdbms-practical/assets/146933698/c21ca842-03fe-4939-975f-e37755b2bda7)

###





### Column-Level Constraints

Column-level constraints are applied to a specific column within a table.

| Constraint       | Description                                                   | Example                                                 |
|-------------------|---------------------------------------------------------------|---------------------------------------------------------|
| NOT NULL          | Ensures that a column cannot have NULL values.                | `CREATE TABLE customers (customer_id INT NOT NULL, name VARCHAR(50));` |
| DEFAULT           | Specifies a default value for a column.                       | `CREATE TABLE messages (message_id INT, content VARCHAR(255) DEFAULT 'No content');` |

### Database-Level Constraints

Database-level constraints involve multiple tables or the entire database.

| Constraint       | Description                                                   | Example                                                 |
|-------------------|---------------------------------------------------------------|---------------------------------------------------------|
| UNIQUE INDEX      | Ensures that values in a column or a combination of columns are unique across tables. | `CREATE UNIQUE INDEX idx_unique_username ON users(username);` |
| CHECK (Database)  | Enforces rules at the database level.                         | `CREATE DATABASE my_database WITH CHECK (compatibility_level >= 130);` |
# 4. View data in the required form using Operators, Functions and Joins.
### Using SQL Operators

Operators are used for operations like arithmetic, comparison, and logical operations.

'''sql
-- Retrieve users with age greater than 25

SELECT * FROM users WHERE age > 25;

-- Combine data from two columns

SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;
### Using SQL Functions

Functions perform computations on data or manipulate data values.

sql
-- Calculate the average salary

SELECT AVG(salary) AS average_salary FROM employees;

-- Extract the year from a date

SELECT EXTRACT(YEAR FROM hire_date) AS hire_year FROM employees;
### Using SQL Joins

Joins combine rows from two or more tables based on a related column.

sql
-- Inner Join: Retrieve orders with customer information

SELECT orders.order_id, customers.customer_name
FROM orders

INNER JOIN customers ON orders.customer_id = customers.customer_id;

-- Left Join: Retrieve all employees and their assigned projects

SELECT employees.employee_id, 
employees.employee_name, projects.project_name
FROM employees
LEFT JOIN employee_projects ON employees.employee_id = employee_projects.employee_id
LEFT JOIN projects ON employee_projects.project_id = projects.project_id;
# ### Using SQL Joins

Joins combine rows from two or more tables based on a related column.

sql
-- Inner Join: Retrieve orders with customer information
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;

-- Left Join: Retrieve all employees and their assigned projects
SELECT employees.employee_id, employees.employee_name, projects.project_name
FROM employees
LEFT JOIN employee_projects ON employees.employee_id = employee_projects.employee_id
LEFT JOIN projects ON employee_projects.project_id = projects.project_id;
### Using SQL Joins

Joins combine rows from two or more tables based on a related column.

sql
-- Inner Join: Retrieve orders with customer information
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;

-- Left Join: Retrieve all employees and their assigned projects
SELECT employees.employee_id, employees.employee_name, projects.project_name
FROM employees
LEFT JOIN employee_projects ON employees.employee_id = employee_projects.employee_id
LEFT JOIN projects ON employee_projects.project_id = projects.project_id;

#5. Creating different types of Views for tailored presentation of data
1. **Simple View:**
   - Based on a single table.
   - Represents a subset of data or specific columns.
   - Useful for simplifying complex queries.

2. **Complex View:**
   - Involves multiple tables.
   - Often created through joins.
   - Provides a consolidated and more comprehensive data set.

3. **Materialized View:**
   - Physically stores the result set.
   - Refreshed periodically.
   - Offers improved query performance, especially for complex queries.

4. **Indexed View:**
   - Similar to a materialized view but includes an index.
   - Enhances query performance for certain types of queries.
   - Requires careful maintenance due to index overhead.

5. **Updatable View:**
   - Allows modification of the underlying data through the view.
   - Must meet specific criteria, such as no joins or aggregations.




