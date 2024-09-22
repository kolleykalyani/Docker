# Docker

### Docker image 

Docker image is a file which contains all binaries, dependencies and configurations which are required to run an application.Docker container is basically a running instance an image.

* To download the image from the docker hub to the terminal 

```
docker pull imagename
```

* To list the docker images 

```
docker images
```

* To list the containers that are running

```
docker ps
```

* To list the containers that are in running state or exited state

```
docker ps -a
```
* to start the container

```
docker start containername/ID
```

* To list only the stopped Docker containers

```
docker ps -a --filter "status=exited"
```

* To list only the running Docker containers

```
docker ps -a --filter "status=running"
```

* Filters containers which share a specific image as an ancestor

```
docker ps --filter ancestor=httpd
```

* To filter and list Docker images that are specifically related to alpine or specific image

```
docker images --filter reference=alpine
```
* To get more info about docker container like ip address

```
docker inspector
```

* To create a container from the specific image we need to run

```
docker run -dt --name containername -p 80:80e imagename/ID
```

* To stop the container

```
docker stop containername/ID
```

* To expose the port number of the container we use "-p" flag.

* -d flag represents the container will be created in detached mode, whcih means it will only create the container but cannot enter into it.

* To see the list of ID's that are associated with the containers which are currently present in the work station.

```
docker container ls -aq
```

* To stop the containers bulky at a time.

```
docker container stop $(docker contaoner ls -aq)
```

* To remove a specific exited container.

```
docker cotainer rm containername/ID
```

* To remove exited containers bulky which are not required.

```
docker container rm $(docker container ls -aq)
```

* To enter inside the container and access the things inside the container we use.

```
docker exec -it containername
```

* To see if the nginx image is running or not inside the container.

```
/etc/init.d/nginx
```

* 
