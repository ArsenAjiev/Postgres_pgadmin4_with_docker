# Postgresql and pgAdmin4

Requirements:

    PostgreSQL


## Quick Start use docker

To get this project up and running locally on your computer:
1. git clone https://github.com/ArsenAjiev/Postgres_pgadmin4_with_docker

```shell
#Run all at once
# without file name
docker-compose up -d --build --force-recreate

# with file name
docker-compose -f docker-compose.dev.yml up -d --build --force-recreate 

```

2. Open a browser to `http://127.0.0.1:5050/` to open the admin site

3. Create server
```text
General:
Name - some name

Connection:
Host name -  name services in docker-compose.yml (db or db1)
Maintenance database - POSTGRES_DB=my_db (default - postgres)
Username - POSTGRES_USER=my_user (default - postgres)
Password - POSTGRES_PASSWORD=my_pass (necessarily)

```

4. Work with DB use shell

```text
# without file name
docker-compose exec db sh

# with file name
docker-compose -f docker-compose.dev.yml exec db1 sh



```

5. Commands
```text
Default > psql -U postgres -d postgres

psql -d database -U user -W	Connects to a database under a specific user	-d: used to state the database name 
-U:used to state the database user
psql -h host -d database -U user -W	Connect to a database that resides on another host	-h: used to state the host 
-d: used to state the database name 
-U:used to state the database user
psql -U user -h host “dbname=db sslmode=require”	Use SSL mode for the connection	-h: used to state the host 
-U:used to state the database user
\c dbname	Switch connection to a new database	 
\l	List available databases	 
\dt	List available tables	 
\d table_name	Describe a table such as a column, type, modifiers of columns, etc.	 
\dn	List all schemes of the currently connected database	 
\df	List available functions in the current database	 
\dv	List available views in the current database	 
\du	List all users and their assign roles	 
SELECT version();	Retrieve the current version of PostgreSQL server	 
\g	Execute the last command again	 
\s	Display command history	 
\s filename	Save the command history to a file	 
\i filename	Execute psql commands from a file	 
\?	Know all available psql commands	 
\h	Get help	Eg:to get detailed information on ALTER TABLE statement use the \h ALTER TABLE
\e	Edit command in your own editor	 
\a	Switch from aligned to non-aligned column output	 
\H	Switch the output to HTML format	 
\q	Exit psql shell	 

```
6. Stop and delete containers 
```shell

# without file name
docker-compose down

# with file name
docker-compose -f docker-compose.dev.yml down

```



## Useful commands for docker 
```shell
# clear ALL data !!! 
docker system prune -a
docker volume prune

```
```shell
# show information 
docker ps -a
docker images
docker volume ls

```


