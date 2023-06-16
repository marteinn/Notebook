# PostgreSQL - Cheat Sheet

## Users

### Common commands

#### List users
- psql=# `\du`

#### List user mappings
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

#### Drop user
  - psql=# `DROP USER example_user;`

### Roles

| On role       | Off role           | Description  |
| ------------- |:-------------:|:-----|
| SUPERUSER | **NOSUPERUSER** | A superuser can override all access restrictions within the database |
| CREATEDB | **NOCREATEDB**  |   Let's a user create databases |
| CREATEROLE | **NOCREATEROLE**  | Permits user to create new roles (that is, execute CREATE ROLE). A role with CREATEROLE privilege can also alter and drop other roles |
| **INHERIT** | NOINHERIT | A role with the INHERIT attribute can automatically use whatever database privileges have been granted to all roles it is directly or indirectly a member of |
| LOGIN | **NOLOGIN** | Allows the user to log in. Roles without this attribute are useful for managing database privileges.

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

### Show all tables and their size

```
select
  table_name,
  pg_size_pretty(pg_relation_size(quote_ident(table_name))),
  pg_relation_size(quote_ident(table_name))
from information_schema.tables
where table_schema = 'public'
order by 3 desc;
```

(Ref https://stackoverflow.com/a/21738505)


## Import/Export

#### Export
  - `pg_dump example_name > example_name.sql`
  - **Examples**:
  - `pg_dump -h localhost -Fc -f backup.sql.tar.gz -U example_user example_db -x -O`

#### Import
- `psql example_name < example_name.sql`
- **Or**:
- `pg_restore --clean -h localhost -d postgres_db -U postgres_user "/shared/dump.sql"`
- **Or**:
- `psql -U postgres_user -d postgres_db -f /shared/dump.sql`


## Versions

### Show postgres (server) version
- `pg_config --version`

### Show postgres (client) version
- `psql --version`


## Guides
- [postgresguide.com](http://postgresguide.com)


## Other Cheat Sheets
- [tomcam.github.io/postgres/](https://tomcam.github.io/postgres/)
