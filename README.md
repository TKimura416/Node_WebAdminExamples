
# Express Admin Examples

This is the examples repository for [Express Admin][1]

Other locations:
- [Introductory Screencast][2]
- [Documentation][3]
- [System Tests][4]

## Install
```bash
$ git clone https://github.com/TKimura416/Node_WebAdminExamples
$ cd Node_WebAdminExamples
$ npm install
```

## Create the schema and the test user
###### MySQL
```sql
CREATE SCHEMA `Node_WebAdminExamples` ;
CREATE USER liolio@localhost IDENTIFIED BY 'karamba' ;
GRANT ALL ON `Node_WebAdminExamples`.* TO liolio@localhost ;
```
###### PostgreSQL
```sql
create database "Node_WebAdminExamples";
-- create schema 'name'; (default: 'public')
create user liolio with password 'karamba';
grant all on database "Node_WebAdminExamples" to liolio;
-- public schema by default
grant all on schema "public" to liolio;
grant all on all tables in schema "public" to liolio;
grant all on all sequences in schema "public" to liolio;
```


## Import the schema and the test data

```bash
# MySQL
$ mysql -p --user=root 'Node_WebAdminExamples' < fixtures/mysql/schema.sql
$ mysql -p --user=root 'Node_WebAdminExamples' < fixtures/mysql/insert.sql
# PostgreSQL
$ sudo -u postgres psql 'Node_WebAdminExamples' < fixtures/pg/schema.sql
$ sudo -u postgres psql 'Node_WebAdminExamples' < fixtures/pg/insert.sql
# SQLite
$ node fixtures/sqlite/import.js
```
For SQLite you need to change the path to the database inside `config/sqlite/config.json`

## Run the Admin
```bash
# MySQL
$ admin config/mysql/
# PostgreSQL
$ admin config/pg/
# SQLite
$ admin config/sqlite/
```

## Navigate to `http://localhost:3000`
Username: **admin**
Password: **11aaAA**


  [1]: https://github.com/TKimura416/Node_WebAdmin
  [2]: http://www.youtube.com/watch?v=1CdoCB96QNk
  [3]: https://github.com/TKimura416/Node_WebAdminTests
