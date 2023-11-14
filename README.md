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

### 3. unique key

creating a table with unique key :-

![Screenshot 2023-11-14 150111](https://github.com/aman7935/rdbms-practical/assets/146933698/1bfbe7bd-6fa8-4083-96ad-4ea33f36ccb7)

Output :-

![Screenshot 2023-11-14 150213](https://github.com/aman7935/rdbms-practical/assets/146933698/42dd83d5-8f1e-4b37-8228-97786278d144)

### check constraints on table level :-
creating table with check constraints :-

![Screenshot 2023-11-14 150703](https://github.com/aman7935/rdbms-practical/assets/146933698/115ba7cc-dc37-46df-afde-de176da9d9c4)

if we enter the age less than 18 it will show error

![Screenshot 2023-11-14 151150](https://github.com/aman7935/rdbms-practical/assets/146933698/2bd805dc-efc4-4fc9-a4f3-98177696aed5)


## Column-Level Constraints
### 1. NOT NULL constraints :-

![Screenshot 2023-11-14 151715](https://github.com/aman7935/rdbms-practical/assets/146933698/2ea7f20e-e244-43f7-ac25-5c619bdbbcae)

A NOT NULL constraint in SQL is a rule that prevents NULL values from being entered into a column within a table. This means that you should provide a valid SQL NOT NULL value to that column in the INSERT or UPDATE statements, as the column will always contain data.

### 2. DEFAULT constraints :-

![Screenshot 2023-11-14 154224](https://github.com/aman7935/rdbms-practical/assets/146933698/bdd25f17-ba86-445c-8f39-cbec953868b3)

it helps to print the values which we declare with DEFAULT keywords.

![Screenshot 2023-11-14 154347](https://github.com/aman7935/rdbms-practical/assets/146933698/73ef0243-1eab-46d5-a122-53dd5af2f5bb)


# 4. View data in the required form using Operators, Functions and Joins.
## Using SQL Operators

Operators are used for operations like arithmetic, comparison, and logical operations.

### 1.Filtering data with WHERE clause

![Screenshot 2023-11-14 155052](https://github.com/aman7935/rdbms-practical/assets/146933698/e5ae2acf-f056-428f-8567-f57512413bb1)

it will show the values in which the salary in employees table is greater than 50000.

### 2.Logical operator

![Screenshot 2023-11-14 155609](https://github.com/aman7935/rdbms-practical/assets/146933698/5caa16b4-44b4-49fa-b91d-d87b2484f822)

it will print only values in which the salary is greater than 50000 or with the city name ludhiana.

### 3.Mathematical operator(perform mathematical operator on numeric columns)

![Screenshot 2023-11-14 155952](https://github.com/aman7935/rdbms-practical/assets/146933698/60a1a866-ced9-4148-aa57-b7f3fedeb15d)

these operators is used when want to multipy the values in columns with specific value. These only can perform numeric functons.

## using functions 
1*String Functions:*
   - CONCAT : Concatenate two or more strings.
   - UPPER and LOWER : Convert a string to uppercase or lowercase.
   - SUBSTRING or SUBSTR : Extract a substring from a string.
   - LENGTH or LEN : Get the length of a string.
   - TRIM: Remove leading and trailing spaces.

2. *Numeric Functions:*
   - SUM, AVG, MIN, MAX : Aggregate functions for sum, average, minimum, and maximum values

3. *Conversion Functions:*
   - CAST or CONVERT: Convert data types.
   - TO_DATE or TO_NUMBER : Convert strings to date or number types.
     
### Using Joins
Join clause use combine rows from two or more table, based on a related column between them

1. Inner join(Inner joins combine records from two tables whenever there are matching values in a field common to both tables)

 ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/59328fe0-0838-4582-af2e-adf7d1f8ccf5)

![Screenshot 2023-11-14 171207](https://github.com/aman7935/rdbms-practical/assets/146933698/29820f40-936f-4ecf-a1ba-42a62b70908f)

Output :-

![Screenshot 2023-11-14 171332](https://github.com/aman7935/rdbms-practical/assets/146933698/8343b279-9dfc-4248-bc03-fb445fa53a5d)

2. left join(LEFT JOIN , also called LEFT OUTER JOIN , returns all records from the left (first) table and the matched records from the right (second) table.)

![Screenshot 2023-11-14 171626](https://github.com/aman7935/rdbms-practical/assets/146933698/0cb9bb5d-9535-47b6-afe6-85cce2f8163f)

output :-

![Screenshot 2023-11-14 171814](https://github.com/aman7935/rdbms-practical/assets/146933698/7fcc457f-89a0-426a-a306-ccb99ddc2845)

3. Right join(The RIGHT JOIN command returns all rows from the right table, and the matching records from the left table. The result is NULL from the left side, when there is no match.)

![Screenshot 2023-11-14 172010](https://github.com/aman7935/rdbms-practical/assets/146933698/3d110ea5-5beb-4b17-a0d8-d971a427b283)

output :-

![image](https://github.com/aman7935/rdbms-practical/assets/146933698/a953a223-d84d-4494-a942-f834412f6966)

4. full join(FULL JOIN creates the result-set by combining results of both LEFT JOIN and RIGHT JOIN)

![Screenshot 2023-11-14 172422](https://github.com/aman7935/rdbms-practical/assets/146933698/82e443e8-2150-4a75-a91a-b5d0c5cd0f95)

Output :-

![image](https://github.com/aman7935/rdbms-practical/assets/146933698/aa483ddd-7399-4c6e-a6ea-faa0f4fa1e61)

#5. Creating different types of Views for tailored presentation of data
1. **Simple View:**

   ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/0b583aca-4609-475a-95d2-0c68203a34ff)


2. **Complex View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/4af23099-6481-47a4-9604-76443db7861c)


3. **Materialized View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/fe74d131-a93d-4aa5-9e86-08da84fcf369)

4. **Indexed View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/bc51dc3b-af87-45ea-84c5-83d675ac3a60)

when we create a view, the view does not store any data by default. So, when we query a view, it actually queries the underlying base table and gets the data. But we can change this default behavior in SQL Server i.e. the SQL Server Views can store the data physically.






