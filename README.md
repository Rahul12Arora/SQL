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
