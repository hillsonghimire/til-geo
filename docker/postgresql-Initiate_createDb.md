## To initiate a new postgresql-postgis database from docker using postgis/postgis:<version> image from docker hub, and initializing the database, under defined `db` and `password`


Use the following docker script
```bash
docker run -d --name <containerName> -p <port_number>:5432 -e POSTGRES_DB=<db_name> -e POSTGRES_PASSWORD=<password> -e POSTGRES_USER=<userInPostgres> postgis/postgis:12-3.0
```

##### Replace the following from above command:
`<containerName>`: replace with the name to assign to docker container
`<port_number>`: replace with the port you want to map the default port from container which is `5432` to port on host machine
`<db_name>`: name of db to create
`<userInPostgres> and <password>`: usename and password that can access the above database.


##### Example:   
```bash
docker run -d --name arena-db -p 5444:5432 -e POSTGRES_DB=arena -e POSTGRES_PASSWORD=arena -e POSTGRES_USER=arena postgis/postgis:12-3.0
``` 

