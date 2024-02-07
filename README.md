# SQL

Relationship database with different tables, cross referencing each others entries with indexes hence relation ship database.

Going Along with MySQL
<ol>
  <li>
    <b>Install MySQL { brew install mysql }</b>
  </li>
  <li>
    <b>Start MySQL server with 
    <ol>
      <li>Homebrew { brew services start/restart mysql }</b></li>
      <li><b>Terminal { sudo mysqld }</b></li>
    </ol>
  </li>
  <li>
    <b>Run SQL command-line terminal { cd /usr/local/Cellar/mysql/8.3.0/bin(optional) ==>  mysql -u root -p passwordIfAny }</b>
  </li>
  <li>
    <b>create database { CREATE DATABASE your_database_name; }</b>
  </li>
  <li>
    <b>use database { USE your_database_name; }</b>
  </li>
  <li>
    <b>drop database { DROP DATABASE your_database_name; }</b>
  </li>
  <li>
    <b>ADD TABLE { CREATE TABLE classRoom (
      rollNo INT
    ) ; }</b>
  </li>
  <li>
    <b>EDIT TABLE { ALTER TABLE classRoom ADD COLUMN(
      name VARCHAR(255)
    ) ; }</b> //255 denotes the character limit length
  </li>
</ol>
