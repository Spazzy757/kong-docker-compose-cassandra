# Docker Kong with Cassandra
docker-compose setup for kong using cassandra and konga as a UI

**kong: 0.11.0**

## Start Up
To start containers and run migrations:
```bash
docker-compose up -d
```
> Cassandra db takes a while to start up, there is a script that checks for cassandra to
go up before kong-migrations runs

To View kong-migrations status:
```bash
docker-compose logs -f kong-migrations
```
> The kong container will fail the first start up, this is becuase kong needs to run migrations
before actually running, once the above commands exits you can run the containers
again, the migrationos will only need to be run once

Finally, Start the containers one last time:
```bash
docker-compose up -d
```

Test Kongs Up:
```bash
curl <docker ip>:8001
```
> This should return the kong admin information

This is a very simple example of a kong 0.11.0 implementation