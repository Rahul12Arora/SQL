# SQL

Relationship database with different tables, cross referencing each others entries with indexes hence relation ship database.

Going Along with MySQL
<ol>
  
  <li>
    <p>Install MySQL { brew install mysql }</p>
  </li>
  
  <li>
    <p>Start MySQL server with 
    <ol>
      <li>Homebrew { brew services start/restart mysql }</p></li>
      <li><p>Terminal { sudo mysqld }</p></li>
    </ol>
  </li>
      
  <li>
    <p>Run SQL command-line terminal { cd /usr/local/Cellar/mysql/8.3.0/bin(optional) ==>  mysql -u root -p passwordIfAny }</p>
  </li>
      
  <li>
    <p>CREATE database { CREATE DATABASE your_database_name; }</p>
  </li>
      
  <li>
    <p>USE database { USE your_database_name; }</p>
  </li>
      
  <li>
    <p>DROP database { DROP DATABASE your_database_name; }</p>
  </li>
      
  <li>
    <p>ADD TABLE { CREATE TABLE classRoom (
      rollNo INT
    ) ; }</p>
  </li>
      
  <li>
    <p>EDIT TABLE { ALTER TABLE classRoom ADD COLUMN(
      name VARCHAR(255)
    ) ; }</p> //255 denotes the character limit length
  </li>
  
  <li>
    <p>DROP TABLE { DROP TABLE classRoom }</p>
  </li>

  <li>
    <p>
    AUTO_INCREMENT ID { CREATE TABLE bands (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    PRIMARY KEY(id)
    )}
    </p>
    <p>
      NOT NULL makes it mandatory to have that field in db
    </br>
      AUTO_INCREMENT increases id by 1 for new document in a table
    </br>
    PRIMARY KEY is used as the primary identfier in the table, querying on this field is faster than querying on other columns
    </p>
  </li>

  <li>
    Use 'Execute SQL script to execute current line/selected code'
  </li>
  
</ol>

**Example**

```
CREATE TABLE bands(
id INT NOT NULL AUTO_INCREMENT,
name VARCHAR(255) NOT NULL,
PRIMARY KEY(id)
);

CREATE TABLE album (
  id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(255) NOT NULL,
  release_year INT,
  band_id INT NOT NULL,
  PRIMARY KEY (id),
  FOREIGN KEY (band_id) REFERENCES bands(id)
);

INSERT INTO bands (name) VALUES('Iron Maiden'); // Add data to table
```

**AI Table**


| Command                             | Description                                            | Example                                                  |
|-------------------------------------|--------------------------------------------------------|----------------------------------------------------------|
| `CREATE DATABASE dbname;`            | Creates a new database.                                | `CREATE DATABASE mydatabase;`                              |
| `USE dbname;`                       | Switches to a specific database.                       | `USE mydatabase;`                                         |
| `SHOW DATABASES;`                   | Lists all databases on the server.                     | `SHOW DATABASES;`                                         |
| `CREATE TABLE tablename (...);`     | Creates a new table.                                   | `CREATE TABLE users (id INT, name VARCHAR(255));`          |
| `SHOW TABLES;`                      | Lists all tables in the current database.              | `SHOW TABLES;`                                            |
| `DESCRIBE tablename;`               | Shows the structure of a table.                        | `DESCRIBE users;`                                         |
| `INSERT INTO tablename VALUES (...);` | Inserts data into a table.                           | `INSERT INTO users VALUES (1, 'John'), (2, 'Jane');`       |
| `SELECT * FROM tablename;`          | Retrieves all records from a table.                   | `SELECT * FROM users;`                                    |
| `UPDATE tablename SET col=value WHERE condition;` | Updates existing records.                  | `UPDATE users SET name='Alice' WHERE id=1;`               |
| `DELETE FROM tablename WHERE condition;`        | Deletes records from a table.                  | `DELETE FROM users WHERE id=2;`                            |
| `ALTER TABLE tablename ADD COLUMN col datatype;` | Adds a new column to a table.                | `ALTER TABLE users ADD COLUMN email VARCHAR(255);`        |
| `DROP TABLE tablename;`              | Deletes a table.                                       | `DROP TABLE users;`                                       |
| `DROP DATABASE dbname;`             | Deletes a database.                                    | `DROP DATABASE mydatabase;`                               |
| `GRANT privileges ON database.table TO 'user'@'host';` | Grants privileges to a user.            | `GRANT SELECT, INSERT ON mydatabase.* TO 'myuser'@'localhost';` |
| `FLUSH PRIVILEGES;`                  | Reloads the privileges from the grant tables.          | `FLUSH PRIVILEGES;`                                       |


Examples:

| Operation           | Description                                                               | Example                                                                                         |
|---------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| SELECT              | Retrieves data from one or more tables                                   | SELECT * FROM employees;                                                                       |
| INSERT INTO         | Inserts new records into a table                                         | INSERT INTO employees (name, age) VALUES ('John', 30);                                           |
| UPDATE              | Modifies existing records in a table                                     | UPDATE employees SET age = 31 WHERE name = 'John';                                               |
| DELETE FROM         | Removes records from a table                                             | DELETE FROM employees WHERE name = 'John';                                                       |
| CREATE TABLE        | Creates a new table in the database                                      | CREATE TABLE employees (id INT PRIMARY KEY, name VARCHAR(50));                                   |
| ALTER TABLE         | Modifies an existing table structure                                     | ALTER TABLE employees ADD COLUMN email VARCHAR(100);                                             |
| DROP TABLE          | Deletes an entire table from the database                                | DROP TABLE employees;                                                                            |
| JOIN                | Combines records from two or more tables based on a related column       | SELECT e.name, d.department_name FROM employees e JOIN departments d ON e.department_id = d.department_id; |
| UNION               | Combines the results of two or more SELECT statements                     | SELECT name FROM employees UNION SELECT name FROM contractors;                                   |
| GROUP BY            | Groups rows that have the same values into summary rows                  | SELECT department_id, AVG(salary) FROM employees GROUP BY department_id;                         |
| ORDER BY            | Sorts the result set by one or more columns                              | SELECT * FROM employees ORDER BY salary DESC;                                                    |
| WHERE               | Filters rows based on a condition                                        | SELECT * FROM employees WHERE age > 30;                                                          |
| DISTINCT            | Returns unique values in the result set                                   | SELECT DISTINCT department_id FROM employees;                                                    |
| HAVING              | Filters records returned by a GROUP BY clause based on specified conditions | SELECT department_id, AVG(salary) FROM employees GROUP BY department_id HAVING AVG(salary) > 50000; |
| IN                  | Determines whether a specified value matches any value in a subquery result | SELECT * FROM employees WHERE department_id IN (SELECT department_id FROM departments WHERE location = 'New York'); |
| EXISTS              | Tests for the existence of any records in a subquery                     | SELECT * FROM employees WHERE EXISTS (SELECT * FROM departments WHERE departments.department_id = employees.department_id); |
| LIKE                | Searches for a specified pattern in a column                              | SELECT * FROM employees WHERE name LIKE 'J%';                                                   |
| BETWEEN             | Selects values within a given range                                      | SELECT * FROM employees WHERE age BETWEEN 25 AND 35;                                            |
| NOT                 | Negates a condition or expresses inequality                              | SELECT * FROM employees WHERE NOT age BETWEEN 25 AND 35;                                        |
| COUNT               | Returns the number of rows in a result set or the number of occurrences of a specified value | SELECT COUNT(*) FROM employees;                                                             |
| SUM                 | Calculates the sum of a set of values                                    | SELECT SUM(salary) FROM employees;                                                               |
| AVG                 | Calculates the average of a set of values                                | SELECT AVG(salary) FROM employees;                                                               |
| MAX                 | Returns the maximum value in a set of values                             | SELECT MAX(salary) FROM employees;                                                               |
| MIN                 | Returns the minimum value in a set of values                             | SELECT MIN(salary) FROM employees;                                                               |
| CONCAT              | Concatenates two or more strings                                          | SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;                           |
| UPPER / LOWER       | Converts a string to uppercase / lowercase                                | SELECT UPPER(name) FROM employees;                                                               |
| SUBSTRING / SUBSTR | Extracts a substring from a string                                        | SELECT SUBSTRING(name, 1, 3) FROM employees;                                                     |
| CASE                | Performs conditional logic in a query                                     | SELECT name, CASE WHEN age < 18 THEN 'Minor' WHEN age >= 18 AND age < 65 THEN 'Adult' ELSE 'Senior' END AS age_group FROM employees; |
| TRUNCATE TABLE      | Removes all rows from a table, but keeps the table structure intact      | TRUNCATE TABLE employees;                                                                        |

