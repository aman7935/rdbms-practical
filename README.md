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
| CREATE                        | Defines new database objects such as tables, indexes, etc. | CREATE TABLE users (id INT PRIMARY KEY, username VARCHAR(50) NOT NULL, email VARCHAR(100) UNIQUE);` |
| ALTER                         | Modifies the structure of an existing database object.    | `ALTER TABLE users ADD COLUMN birthdate DATE; |
| DROP                          | Deletes a database object (e.g., table, index).           | `DROP TABLE users;                          |

| Data Manipulation Language (DML) | Description                                   | Example                                        |
|----------------------------------|-----------------------------------------------|------------------------------------------------|
| SELECT                           | Retrieves data from one or more tables.      | SELECT * FROM users WHERE age > 21;`           |
| INSERT                           | Adds new records into a table.               | `INSERT INTO users (username, email) VALUES ('JohnDoe', 'john@example.com'); |
| UPDATE                           | Modifies existing records in a table.        | `UPDATE users SET age = 25 WHERE username = JohnDoe; |
| DELETE                           | Removes records from a table.                | `DELETE FROM users WHERE username = JohnDoe'; |

| Data Control Language (DCL) | Description                                | Example                                           |
|-----------------------------|--------------------------------------------|---------------------------------------------------|
| GRANT                       | Provides specific privileges to users.     | GRANT SELECT, INSERT ON users TO employee_role;` |
| REVOKE                      | Withdraws previously granted permissions. | REVOKE INSERT ON users FROM employee_role;`      |
| DENY                        | Explicitly denies certain permissions.      | DENY DELETE ON users TO temporary_user;`         |
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

# 6. How to apply Conditional Controls in PL/SQL

## there are two types of condition control statements(IF statement and CASE statements)
### IF statements can be further divided into 3 parts
1. IF-THEN

example :-

![Screenshot 2023-11-15 114207](https://github.com/aman7935/rdbms-practical/assets/146933698/7b8aa56a-2f9b-4026-8a58-299419404a3f)

OUTPUT :-

![Screenshot 2023-11-15 114700](https://github.com/aman7935/rdbms-practical/assets/146933698/2fc4d91a-2809-436f-87d9-7d03243c1a7e)

2. IF-THEN-ELSE

example :-

![Screenshot 2023-11-15 115222](https://github.com/aman7935/rdbms-practical/assets/146933698/dfa5b023-4388-4061-be40-d92ab7c5c791)

OUTPUT :-

![Screenshot 2023-11-15 115310](https://github.com/aman7935/rdbms-practical/assets/146933698/745105c8-8f34-4d68-8e46-571b0110596c)

3. IF-THEN-ELSIF

example :-

![Screenshot 2023-11-15 115629](https://github.com/aman7935/rdbms-practical/assets/146933698/cbbbbb77-fdc1-48a2-8b90-b6f9f6797e38)

OUTPUT :-

![Screenshot 2023-11-15 115640](https://github.com/aman7935/rdbms-practical/assets/146933698/287a0f56-b17d-4357-bb2b-9260c803eecb)

## 2. CASE STATEMENT

EXAMPLE :-

![Screenshot 2023-11-15 120336](https://github.com/aman7935/rdbms-practical/assets/146933698/fccc7235-93be-4479-bad9-9db1bcda3562)

OUTPUT :-

![Screenshot 2023-11-15 120401](https://github.com/aman7935/rdbms-practical/assets/146933698/49b1b281-9403-459a-8d40-920e6d6bd47b)

## SEARCHED CASE STATEMENT

![Screenshot 2023-11-15 120810](https://github.com/aman7935/rdbms-practical/assets/146933698/f349f183-3688-42e1-86a3-36fb20c54368)

output :-

![Screenshot 2023-11-15 120830](https://github.com/aman7935/rdbms-practical/assets/146933698/ee31b541-16b9-4fd3-ae87-7052834e1f2f)
# 7. Error Handling using Internal Exceptions and External Exceptions

## Internal exceptions/system defined exceptions(Defined by oracle)
### 1. NO_DATA_FOUND EXCEPTION

EXAMPLE :-

first we have created and inserted data in table :-

![Screenshot 2023-11-15 132759](https://github.com/aman7935/rdbms-practical/assets/146933698/680f70c6-082d-4837-9629-6b97348e50c7)

now we will write exception handling code for no data :-

![Screenshot 2023-11-15 132950](https://github.com/aman7935/rdbms-practical/assets/146933698/930eb9f5-0d4e-4c0c-870e-e803c2712a66)

output :-

![Screenshot 2023-11-15 133017](https://github.com/aman7935/rdbms-practical/assets/146933698/585bd139-f816-4894-9e9d-b11de5ef6aac)

### 2. ZERO_DIVIDE exception

creating and insertin values in table  :-

![Screenshot 2023-11-15 133617](https://github.com/aman7935/rdbms-practical/assets/146933698/d93dad89-05d7-4b78-9362-e9b8f9329436)

writing exception :-

![Screenshot 2023-11-15 133709](https://github.com/aman7935/rdbms-practical/assets/146933698/6b06d7c4-3193-43eb-aa3e-c3557d10afe2)

output :-

![Screenshot 2023-11-15 133748](https://github.com/aman7935/rdbms-practical/assets/146933698/4c9e28c3-395f-4d55-9099-dc2be6410938)

## 2. External exceptions( user defined exceptions)

1. Raise exception
 
![Screenshot 2023-11-15 141128](https://github.com/aman7935/rdbms-practical/assets/146933698/a577d9ce-9156-4af2-a148-1d0d71d011b1)

output :-

![Screenshot 2023-11-15 141152](https://github.com/aman7935/rdbms-practical/assets/146933698/1d93b0bd-a515-4d41-8027-c498b219ff01)

2. Raise_application_error

![Screenshot 2023-11-15 142453](https://github.com/aman7935/rdbms-practical/assets/146933698/670f5ec1-1f65-41e4-9c0f-388940af8b86)

output :-

![Screenshot 2023-11-15 142531](https://github.com/aman7935/rdbms-practical/assets/146933698/08ffbcb4-9d68-4cc7-b597-602a38b58cb8)

# 8. Using various types of Cursors
## A cursor is a pointer to this context area. PL/SQL controls the context area through a cursor. A cursor holds the rows (one or more) returned by a SQL statement. The set of rows the cursor holds is referred to as the active set.

two types of cursors
1. Impicit cursors
2. explicit cursors

### implicit Attribute & Description
1	
%FOUND

Returns TRUE if an INSERT, UPDATE, or DELETE statement affected one or more rows or a SELECT INTO statement returned one or more rows. Otherwise, it returns FALSE.

2	
%NOTFOUND

The logical opposite of %FOUND. It returns TRUE if an INSERT, UPDATE, or DELETE statement affected no rows, or a SELECT INTO statement returned no rows. Otherwise, it returns FALSE.

3	
%ISOPEN

Always returns FALSE for implicit cursors, because Oracle closes the SQL cursor automatically after executing its associated SQL statement.

4	
%ROWCOUNT

Returns the number of rows affected by an INSERT, UPDATE, or DELETE statement, or returned by a SELECT INTO statement.

### SQL%ROWCOUNT attribute to determine the number of rows affected −

![Screenshot 2023-11-16 100114](https://github.com/aman7935/rdbms-practical/assets/146933698/89c362bd-2a4b-4fe6-9789-6a5adb080343)

OUTPUT:-

![Screenshot 2023-11-16 100302](https://github.com/aman7935/rdbms-practical/assets/146933698/a348cad7-fd0b-442b-9768-e6a96d1958bd)

### Explicit Cursors

Explicit cursors are programmer-defined cursors for gaining more control over the context area. An explicit cursor should be defined in the declaration section of the PL/SQL Block. It is created on a SELECT Statement which returns more than one row.

Declaring the Cursor

![Screenshot 2023-11-16 100544](https://github.com/aman7935/rdbms-practical/assets/146933698/03dee94e-2701-44a1-8327-4aef56a30c6c)

Opening the Cursor

![Screenshot 2023-11-16 100615](https://github.com/aman7935/rdbms-practical/assets/146933698/c5878905-55bd-45dc-beee-476076b76d0a)

Fetching the Cursor

![Screenshot 2023-11-16 100641](https://github.com/aman7935/rdbms-practical/assets/146933698/f25a1c39-7c26-4f64-a80d-3d3df74afd62)


Closing the Cursor

![Screenshot 2023-11-16 100740](https://github.com/aman7935/rdbms-practical/assets/146933698/a90c5164-82b4-4b58-824c-229e955332b0)

# 9. How to run Stored Procedures and Functions

## 1. procedures 

A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

example :-

![Screenshot 2023-11-16 102457](https://github.com/aman7935/rdbms-practical/assets/146933698/3452cae0-6511-4bb6-8174-8ff24325cfc9)

executing a stored procedure

![Screenshot 2023-11-16 102617](https://github.com/aman7935/rdbms-practical/assets/146933698/4bf1208f-d832-441c-b040-b42e86ad98ca)

## 2. Stored functions 

Creating the stored function

![Screenshot 2023-11-16 104018](https://github.com/aman7935/rdbms-practical/assets/146933698/050acaf9-7895-48f7-92b1-80f529aa7232)

Using the stored function

![Screenshot 2023-11-16 104111](https://github.com/aman7935/rdbms-practical/assets/146933698/b7386d40-73ce-4da9-ba4b-eb33cca20a20)

# 10. Creating Packages and applying Triggers

1. Create pacakge specification

![Screenshot 2023-11-16 110230](https://github.com/aman7935/rdbms-practical/assets/146933698/5336a6ca-721d-4180-904a-1328ecfafe88)


2. create Package body

![Screenshot 2023-11-16 110252](https://github.com/aman7935/rdbms-practical/assets/146933698/a53f253d-31fe-47c1-b38c-4619c9a185d3)


#  Applying Triggers
## Row level trigger

![image](https://github.com/aman7935/rdbms-practical/assets/146933698/d261b4a6-ef1f-4715-9310-53a66640e486)

## column level trigger

![Screenshot 2023-11-16 115101](https://github.com/aman7935/rdbms-practical/assets/146933698/c27f1bfe-c197-42ec-b0b1-a3e782c0b047)
# 11. Creating Arrays and Nested Tables.
creating arrays

![Screenshot 2023-11-16 120412](https://github.com/aman7935/rdbms-practical/assets/146933698/0b03b041-bc48-48d2-883c-86ab588163de)

## Nested table
![Screenshot 2023-11-16 121359](https://github.com/aman7935/rdbms-practical/assets/146933698/7948d9e9-cd92-4a09-9552-9f92d82f9744)

