## To run the database in Docker, you need to execute these commands:

### Create a volume for the database:
```
docker volume create postgres13_data
```

### Start the container:
```
docker run --name postgres13 -d \
-e POSTGRES_PASSWORD=password \
-e POSTGRES_USER=user \
-e POSTGRES_DB=postgres \
-e PGDATA=/var/lib/postgresql/data/pgdata \
-v postgres13_data:/var/lib/postgresql/data/pgdata \
-v "/directory-with-init-scripts":/docker-entrypoint-initdb.d \
-p 5432:5432 \
postgres:13-alpine
```
