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

sudo docker rmi -f $(sudo docker images -aq)

sudo docker build -t my-app:1.4 .

sudo docker tag my-app:1.4 santhosh27sg/my-app:1.4

sudo docker push santhosh27sg/my-app:1.4


sudo docker-compose -f docker-compose.yaml up

sudo sh
[sudo] password for santhoshkumar: 
# cd docker
# ls
buildkit  containers  engine-id  image  network  overlay2  plugins  runtimes  swarm  tmp  volumes
# cd volumes
# ls
1fb4d20392c5774076fe3e1da746758a707baed1703482180727986186ba9d68  backingFsBlockDev
250e8f4d9238e4b61c5a12ce69e491ec45a2135bdd84ff723e796c9ae03a2da5  docker-fullstack_mongo-data
2b39f6ece9eec4d9898b8551747113ddae15072648bcda2bc3f038a5ae0b9963  e3c0754cf3fadef02a2add6f1d243c5c132816f451b7550208b85909924db277
2d97b7baed910275dc7f1b57d052a6b5975b5a251f9c9a742071e34996442712  metadata.db
680cfa9aaa190367c097fb5532cd4e9a01c00ebdaeaba0acc1007d33d9d155c9
# 