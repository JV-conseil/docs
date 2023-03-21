---
sort: 1
title: PostgreSQL 🐘 Cheatsheet
---

<!-- markdownlint-disable MD025 MD026 MD033 MD041 -->

<a href="https://www.postgresql.org/docs/15/" target="_blank" title="PostgreSQL v15 Documentation"><img src="https://www.postgresql.org/media/img/about/press/elephant.png" align="right" alt="PostgreSQL Banner with Logo, Elephant and Slogan" height="100"></a>

<!-- omit in toc -->
# PostgreSQL 🐘 Cheatsheet

[![PostgreSQL 15.2](https://img.shields.io/badge/PostgreSQL-15.2-green.svg)](https://www.postgresql.org/docs/15/)
[![License EUPL 1.2](https://img.shields.io/badge/License-EUPL--1.2-blue.svg)](LICENSE)
[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil "Become a sponsor to JV-conseil")
[![Follow JV conseil on StackOverflow](https://img.shields.io/stackexchange/stackoverflow/r/2477854)](https://stackoverflow.com/users/2477854/jv-conseil "Follow JV conseil on StackOverflow")
[![Follow JVconseil on Twitter](https://img.shields.io/twitter/follow/JVconseil.svg?style=social&logo=twitter)](https://twitter.com/JVconseil "Follow JVconseil on Twitter")
[![Follow JVconseil on Mastodon](https://img.shields.io/mastodon/follow/109896584320509054?domain=https%3A%2F%2Ffosstodon.org)](https://fosstodon.org/@JVconseil "Follow JVconseil@fosstodon.org on Mastodon")
[![Follow JV conseil on GitHub](https://img.shields.io/github/followers/JV-conseil?label=JV-conseil&style=social)](https://github.com/JV-conseil "Follow JV-conseil on GitHub")

<!-- omit in toc -->
## Table of Content

- [Database](#database)
- [Table](#table)
- [User](#user)
- [How To Delete Duplicate Rows in PostgreSQL](#how-to-delete-duplicate-rows-in-postgresql)
- [Show active sessions on a database](#show-active-sessions-on-a-database)
- [Replicate Databases over Servers with `pg_dump` command](#replicate-databases-over-servers-with-pg_dump-command)
- [Change Table \& Sequence ownership](#change-table--sequence-ownership)
- [CSV \& JSON Gzip Data Dump](#csv--json-gzip-data-dump)
- [Timezone](#timezone)

## Database

| Command                                                             | Description                                                                                                            |
| :------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------- |
| `\l+`                                                               | List all databases                                                                                                     |
| `\c database_name`                                                  | Connect to database_name                                                                                               |
| `CREATE DATABASE database_name WITH TEMPLATE another_database_name` | Create a database with another database structure<br> and data within the same server                                  |
| `DROP DATABASE IF EXISTS database_name`                             | Delete a database                                                                                                      |
| `ALTER DATABASE database_name RENAME TO database_new_name`          | Rename a database                                                                                                      |
| `VACUUM FULL VERBOSE ANALYZE`                                       | Optimize database                                                                                                      |
| `show all`                                                          | Display configuration parameters                                                                                       |
| `pg_dump database \| gzip -9 > database.bak.sql.gz`                 | Database Backup                                                                                                        |
| `REASSIGN OWNED BY one_user TO another_user`                        | Change the ownership of database objects owned by a database role (works at database level once inside it \c database) |
| `DROP OWNED BY one_user`                                            | Can safely come after the `REASSIGN OWNED BY` command                                                                  |

## Table

| Command                                                                 | Description           |
| :---------------------------------------------------------------------- | :-------------------- |
| `\dt+`                                                                  | Show all tables       |
| `DROP TABLE IF EXISTS table_name`                                       | Delete a table        |
| `\copy (SELECT * FROM table_name) TO 'file_path_and_name.csv' WITH CSV` | Export a table as CSV |

## User

| Command                                                          | Description                                       |
| :--------------------------------------------------------------- | :------------------------------------------------ |
| `\du+`                                                           | List all users                                    |
| `CREATE USER user_name WITH PASSWORD '****'`                     | Create a user                                     |
| `DROP USER user_name`                                            | Delete an user                                    |
| `ALTER ROLE user_name SET client_encoding TO 'utf8'`             | Change encoding for an user                       |
| `ALTER ROLE user_name SET timezone TO 'UTC'`                     | Change timezone for an user                       |
| `ALTER ROLE user_name WITH PASSWORD '****'`                      | Change a user password                            |
| `ALTER ROLE name RENAME TO new_name`                             | Change a user name                                |
| `GRANT ALL PRIVILEGES ON DATABASE database_name TO user_name`    | Extend user privileges                            |
| `REVOKE ALL PRIVILEGES ON DATABASE database_name FROM user_name` | Remove privileges from user                       |
| `COMMENT ON ROLE role_name IS 'description text'`                | Add description to `role`, `table`, `database`... |
| `SELECT usename, useconfig FROM pg_shadow`                       | View users parameters                             |
| `GRANT pg_read_all_stats TO user_name`                           | Add access privileges to an user (1)              |
| `REVOKE pg_read_all_stats FROM user_name`                        | Remove access privileges                          |

*(1) PostgreSQL provides a set of [default roles](https://www.postgresql.org/docs/13/default-roles.html)
which provide access to certain, commonly needed, privileged capabilities and information*

## How To Delete Duplicate Rows in PostgreSQL

```sql
python manage.py dbshell
--
-- Views duplicate rows
--
SELECT title, COUNT(DISTINCT(id)), LEFT(abstract, 50) AS abstract
FROM publications GROUP BY title, abstract
HAVING COUNT(DISTINCT(id)) > 1 ORDER BY title, abstract DESC ;
SELECT title FROM publications WHERE id IN (
    SELECT id FROM (SELECT id, ROW_NUMBER() OVER (
        PARTITION BY title, abstract ORDER BY abstract DESC
    ) AS row_num FROM publications
) t WHERE t.row_num > 1) ;
--
-- Deleting duplicate rows using subquery
--
DELETE FROM publications WHERE id IN (
    SELECT id FROM (SELECT id, ROW_NUMBER() OVER (
        PARTITION BY title, abstract ORDER BY abstract DESC
    ) AS row_num FROM publications
) t WHERE t.row_num > 1) ;
\q
```

*src: How To Delete [Duplicate Rows](http://www.postgresqltutorial.com/how-to-delete-duplicate-rows-in-postgresql/) in PostgreSQL.*

## Show active sessions on a database

List active sesssions on databases

```sql
SELECT pid AS process_id,
       usename AS username,
       datname AS database_name,
       client_addr AS client_address,
       application_name,
       backend_start,
       state,
       state_change
FROM pg_stat_activity ;
```

Kill idle ones:

```sql
SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE datname IN ('database1', 'database2') ;
```

*src: Show [active sessions](https://dataedo.com/kb/query/postgresql/list-database-sessions)
on a database*

## Replicate Databases over Servers with `pg_dump` command

```sql
CREATE DATABASE database_name ;
GRANT ALL PRIVILEGES ON DATABASE database_name TO user_name ;
```

```bash
PGPASSWORD="****" pg_dump --clean --no-owner --no-privileges --verbose -C \
-h myPgServer.postgres.database.azure.com -U user_name database_name |\
PGPASSWORD="***" psql -h myOtherPgServer.postgres.database.azure.com -U user_name database_name
```

```sql
ALTER DATABASE database_name RENAME TO database_new_name ;
```

*src: [pg_dump](https://www.postgresql.org/docs/13/app-pgdump.html) extract
a PostgreSQL database into a script file or other archive file.*

*src: How to copy a [database to another server](https://www.postgresqltutorial.com/postgresql-copy-database/).*

## Change Table & Sequence ownership

```sql
-- ALTER TABLE
SELECT 'ALTER TABLE '|| schemaname || '."' || tablename ||'" OWNER TO <NEW_OWNER_ROLE> ;'
FROM pg_tables WHERE NOT schemaname IN ('pg_catalog', 'information_schema')
ORDER BY schemaname, tablename;
-- ALTER SEQUENCE
SELECT 'ALTER SEQUENCE '|| sequence_schema || '."' || sequence_name ||'" OWNER TO <NEW_OWNER_ROLE> ;'
FROM information_schema.sequences WHERE NOT sequence_schema IN ('pg_catalog', 'information_schema')
ORDER BY sequence_schema, sequence_name;
-- REASSIGN OWNED
\c database_name ;
REASSIGN OWNED BY one_user TO another_user ;
```

## CSV & JSON Gzip Data Dump

*Optionally with Django*

```bash
python manage.py dbshell
```

```sql
-- EXPORT QUERY TO GZIP CSV DUMP
\copy (SELECT id, title, ... FROM some_table WHERE id NOT LIKE 'CRITERIA-%' ORDER BY id)
TO PROGRAM 'gzip > ~/path-to-a-dump-data-folder/dump_`date +"%Y%m%d_%H%M%S"`.csv.gz'
WITH (FORMAT CSV, HEADER, FORCE_QUOTE(title)) ;
```

*src: [Export to CSV and Compress with GZIP in Postgres.](https://stackoverflow.com/a/72275790/2477854)*

```sql
-- EXPORT QUERY GZIP JSON DUMP
\copy (SELECT JSON_AGG(ROW_TO_JSON(T)) :: text FROM
(SELECT id, title, ... FROM some_table WHERE id NOT LIKE 'CRITERIA-%' ORDER BY id) AS T)
TO PROGRAM 'gzip > ~/path-to-a-dump-data-folder/dump_`date +"%Y%m%d_%H%M%S"`.json.gz' ;
```

*src: [How to export PostgreSQL data to a JSON file.](https://alphahydrae.com/2021/02/how-to-export-postgresql-data-to-a-json-file/)*

## Timezone

Diagnosis

```sql
SHOW timezone ;
SELECT * FROM pg_timezone_names ;
```

<!-- omit in toc -->
## References 📚

- PostgreSQL 14.4 [Documentation](https://www.postgresql.org/docs/14/) (postgresql.org).
- PostgreSQL interactive terminal [psql](https://www.postgresql.org/docs/current/app-psql.html) (postgresql.org).
- Django [PostgreSQL notes](https://docs.djangoproject.com/en/4.0/ref/databases/#postgresql-notes) (docs.djangoproject.com).
- Postgres [Cheat Sheet](https://postgrescheatsheet.com/#/tables).

<!-- omit in toc -->
## Sponsorship

If this project helps you, you can offer me a cup of coffee ☕️ :-)

[![Become a sponsor to JV-conseil](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/JV-conseil)
