## container

## create docker network

docker network create mongo-network

## start mongo

    docker run -d \
    -p 27017:27017 \
    -e MONGO_INITDB_ROOT_USERNAME=admin \
    -e MONGO_INITDB_ROOT_PASSWORD=password \
    --name mongodb \
    --net mongo-network
    mongo    

## start mongo-express

    docker run -d \
    -p 8081:8081 \
    -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
    --net mongo-network \
    --name mongo-express \
    -e ME_CONFIG_MONGODB_SERVER=mongodb \
    mongo-express 

## with auto mate of start all containers

 sudo docker-compose -f docker-compose.yaml up

sudo docker-compose -f docker-compose.yaml up -d

sudo docker-compose -f docker-compose.yaml down
 up or down
