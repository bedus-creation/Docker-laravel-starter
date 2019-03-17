1. Get the docker container
```
Dcoker ps
```
2. Docker Images
```
docker image ls
```
3. Sharing and Running the docker file
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

