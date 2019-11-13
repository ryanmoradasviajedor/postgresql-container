# Database Container
This is database container running PostgreSQL.

## Controlling Database Container
### Create docker network
If you have not created a docker network named `local-net`, create it with the command below.  
If you already have it, skip to "Create & Start Container" section.

```
docker network create --driver bridge local-net
```

To see if it is created successfully, execute below.
```
docker network ls
```

If you want to remove the network, this is the command to do it.
```
docker network rm <network_name>
```

### Create & Start Container
Execute the command below in the directory where docker-compose.yml file resides.
This command creates and runs a container based on the configuration in this yml file.
```
docker-compose up -d
```

### Stop Container
Stopping container does NOT delete the container but shuts down.
```
docker-compose stop
```

### Start Container
Stopped container can be started again by start command.
```
docker-compose start
```

### Delete Container
Deleting container. This command will preserve the database content.
```
docker-compose down
```

To delete the database content also, add `-v` option to delete it together.
```
docker-compose down -v
```


## Connect to the PostgreSQL Container

### Connect from Other Container
Below is the command to login to PostgreSQL on the container from the other container.  
The host name of the database container is `postgre-db`.

```
psql -h localhost -p 54320 -U john -d mydb
```

* `-h`:  The database server.

* `-p`: The port PostgreSQL is running on.

* `-U`: The username.

* `-d`: The database name.

After you run this command, you will be asked to enter a password.

CREATE DATABASE dbname;
## Creating PostgreSQL Database
Login to PostgreSQL by executing the command above.  
Create DB user and database for your project.

**Syntax**
The basic syntax of CREATE DATABASE statement is as follows −

```
CREATE DATABASE dbname;
```

where `dbname` is the name of a database to create.
