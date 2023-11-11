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

To delete all containers including its volumes use,

docker rm -vf $(docker ps -aq)
To delete all the images,

docker rmi -f $(docker images -aq)
Remember, you should remove all the containers before removing all the images from which those containers were created.

sudo docker rm -vf $(sudo docker ps -aq)

sudo docker rmi -f $(sudo ddocker images -aq)

sudo docker build -t my-app:1.4 .

sudo docker tag my-app:1.4 santhosh27sg/my-app:1.4

sudo docker push santhosh27sg/my-app:1.4


sudo docker-compose -f docker-compose.yaml up