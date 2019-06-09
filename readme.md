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
Dcoker ps
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
docker run -d --rm -p 8080:80 -v $(pwd)/application:/var/www/htmlpublic shippingdocker/app:latest nginx
```
4. docker exac

5. Docker Stop
```
docker stop [ID]
```
6. Watch the current running process
```
ps aux
```


