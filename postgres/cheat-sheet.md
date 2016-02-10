# PostgreSQL - Cheat Sheet

## Users

### Common commands

#### List users
  - psql=# `\deu+` _List of user mappings_
  - **(OR)**
  - `psql -c '\deu+'`

#### Create user
  - psql=# `CREATE USER example_user WITH PASSWORD 'example_password';` ([docs](http://www.postgresql.org/docs/current/static/sql-createuser.html))

#### Assign user to database
  - psql=# `GRANT ALL PRIVILEGES ON DATABASE "example_database" to example_user;`

#### Make user superuser
  - psql=# `ALTER USER example_user WITH SUPERUSER`;

#### Remove superuser permission
  - psql=# `ALTER USER example_user WITH NOSUPERUSER;`

#### Let user create databases
  - psql=# `ALTER USER example_user WITH CREATEDB`;

### Roles

On role | Off role | Description  |
--- | --- | --- | ---
SUPERUSER | **NOSUPERUSER** | A superuser can override all access restrictions within the database | NOSUPERUSER
CREATEDB | **NOCREATEDB** | Let's a user create databases
CREATEROLE | **NOCREATEROLE** | Permits user to create new roles (that is, execute CREATE ROLE). A role with CREATEROLE privilege can also alter and drop other roles
**INHERIT** | NOINHERIT | A role with the INHERIT attribute can automatically use whatever database privileges have been granted to all roles it is directly or indirectly a member of
LOGIN | **NOLOGIN** | Allows the user to log in. Roles without this attribute are useful for managing database privileges.

##  Databases

### Common commands

#### Create database
  - psql=# `CREATE DATABASE example_database;`
  - **(OR)**
  - `createdb example_database`

#### Create database with another type+collate
  - psql=# `CREATE database example_database with ENCODING='UTF-8' LC_CTYPE='sv_SE.utf8' LC_COLLATE='sv_SE.utf8' template=template0;`

#### List databases
  - psql=# `\l+` _List databases_

#### Rename database
  - psql=# `ALTER DATABASE example_name RENAME TO example_name_backup;`

#### Connect to database
  - psql=# `\c exmple_database`

## Tables

### Common commands

#### List tables
  - _(First connect to db)_
  - psql=# `dt`

## Import/Export

#### Export
`pg_dump example_name > example_name.sql`

#### Import
`psql example_name < example_name.sql`

## Guides
- [postgresguide.com](http://postgresguide.com)
