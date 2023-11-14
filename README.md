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
