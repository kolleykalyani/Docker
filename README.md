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
docker run -dt --name containername -p 80:80 imagename/ID
```

* To stop the container

```
docker stop containername/ID
```




