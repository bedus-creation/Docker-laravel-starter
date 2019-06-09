### Docker Image 
An image is a combination of a file system and parameters
* List Docker Image
```
docker image ls
```

### Docker Container
Containers are instances of Docker images that can be run using the Docker run command. The basic purpose of Docker is to run containers.

* Get the docker container
```
docker ps
```

* Update Docker
```
docker build -t shippingdocker/app:latest \
    -f docker/app/Dockerfile \
    docker/app
```
* Run the docker Container
```
docker run --rm -it shippingdocker/app:latest bash
```
* Sharing and Running the docker file
```
docker run -d --rm -p 8080:80 -v "$(pwd)/application:/var/www/html/public" shippingdocker/app:latest nginx
```
* docker exac
```
```
* Watch the current running process
```
ps aux
```
* Statistics of a running container.
```
docker stats ContainerID 
```
* Process with in the container
```
docker top ContainerID 
```
* Docker Stop
```
docker stop [ID]
```
* Remove the container
```
docker rm ContainerID 
```

### Docker Network 
* List networks
```
docker network ls
```
* Create a network
```
docker network create appnet
```
* Add 
```
docker run --rm -d \
    --name=app \
    --network=appnet\
     shippingdocker/app:latest

docker run --rm -d \
    --name=mysql \
    --network=appnet \
    -e MYSQL_ROOT_PASSWORD=root \
    -e MYSQL_DATABASE=homestead \
    -e MYSQL_USER=homestead \
    -e MYSQL_USER_PASSWORD=secret \
    mysql:5.7
```
* Inspect a network
```
docker network inspect networkname 
```
### Connection Docker network
* Create laravel application
```
docker run -it --rm -v $(pwd):/var/www/html \
    -w /var/www/html \
    shippingdocker/app:latest \
    composer create-project laravel/laravel application
```
* Run the laravel application in deamon
```
docker run --name=app --network=appnet -d --rm -p 8080:80 -v "$(pwd)/application:/var/www/html/application/" shippingdocker/app:latest
```
* Run the php artisan commmand 
```
docker exec -it -w /var/www/html/application/ app php artisan list
```
