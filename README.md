# commands

## create docker 
network docker network create mongo-network

## start mongodb 
docker run -d \
-p 27017:27017 \ 
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \ 
--net mongo-network \
--name mongodb \
mongo

## start mongo-express
docker run -d \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
--net mongo-network \
--name mongo-express \
mongo-express

# YAML File
first we have to write file manually
### run command
```
sudo docker-compose -f mongo.yaml up -d
```
```
sudo docker-compose -f mongo.yaml down
```

### Mongo
mongo express is up on:
```
http://localhost:8080/
```