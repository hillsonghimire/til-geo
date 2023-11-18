## Create docker pgadmin4 instance, and connect to running postgresql-server on different container locally

This assumes that the postgresql database is setup and running in different container. To setup the container visit: -  [postgis setup, one liner](docker/postgresql-Initiate_createDb.md)


```bash
# download postgresql
docker pull dpage/pgadmin4

# run the above downloaded image
docker run -p 80:80 \
    -e 'PGADMIN_DEFAULT_EMAIL=<UserEmail>' \
    -e 'PGADMIN_DEFAULT_PASSWORD=<UserPassword>' \
    -d dpage/pgadmin4
# Replace <UserEmail> and <UserPassword> from above
```
#### To connect pgadmin to the db server:
1. head over to the `<Ip Addr>:80` to browser pgadmin homepage
2. use `username and pw` from configured earlier
3. configure new server (Register-Server)
    - the connection takes the host IP address
    - configure the running port, username, and password correctly.

Connection should be successful.