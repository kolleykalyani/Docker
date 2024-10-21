# Docker

### what is container ?

The word “container” doesn’t mean anything super precise. Basically there are a few new Linux kernel features (“namespaces” and “cgroups”) that let you isolate processes from each other. When you use those features, you call it “containers”.

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

* To Remove the stopped containers

```
docker system prune
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

* "-i" flag keeps stdin open if not attached.

* "-t" flag allocates a pseudo tty.

* To overwrite the default container command that is present in the docker image

```
docker container run -d imagename sleep500 (default container command )
```
### Note: If the sleep500 completes then the pid1 running will be exited then the container also will be exited. 

* To know the cpu utilization of conatiner we need to install htop tool inside the container then just type htop we can see the things.(it works for single container)

```
htop
```

* By default, docker containers will not start when they exit or when docker daemon is restarted. Docker provides restart policies to control whether your container will automatically when they exot or restarted.

* We can specify the restart policy by using --restart flag with docker run command.

*  "no" flag : do not automatically restart the container (the default one).

*  "on-failure" : restart the container if it exits due to an error, which manifests as a non-zero exit code.

*  "unless-stopped" : restart the container unless it is explicitly stopped or docker itself is stopped or restarted.

*  "always" : aleways restart the container if it stops.

*  To restart the container to automatically restart if container or daemon is restarted or it is stopped.

```
docekr container run -d --restart unless-stopped imagename
```

* To know the docker components level of disk usage or disk metrix of docker components and containers

```
docker system df
```

* To create a file inside the container.

```
dd if=/dev/zero of=bigfile.txt bs=1M count=500
```

* dd: A Unix utility used to convert and copy files, often used for tasks like creating disk images or large files for testing purposes.

* if=/dev/zero: The input file (if=) is /dev/zero, which is a special file in Unix-like systems that provides an endless stream of null (zero) bytes.

* of=bigfile.txt: The output file (of=) is bigfile.txt. This is where the data from /dev/zero will be written, creating a file filled with zero bytes.

* bs=iM: This specifies the block size (bs=) for the dd command.where M refers to megabytes). It sets the amount of data to read and write in each block. For example, bs=1M would mean 1 megabyte per block.

* count=500: This specifies the number of blocks to copy. In this case, it would copy 500 blocks of size bs.

* If teh ten containers are running and we want to know which container is using more disk usage and to know component level disk usage 

```
docker system df -v
```

* To automatically remove a container when it exits after the job is done

```
docker container run -dt --rm --name containername imagename defaultcommand 
```

### Docker file 

* Docker file is a text document that contains all the commands a user could call on the command line to assemble an image.

* To build the docker or do the docker build

```
docker build -t imagename .
```

* COPY and ADD both are dockerfile instructions that server similar purposes. They let us copy files from a specific location to docker image.

### Difference b/w COPY and ADD ?

* **COPY** takes in source and destination. It only let us copy in a  local file or directory from our host.

* **ADD** also does the same but supports another 2 features.

> We can use an URL instead of file or directory.
> Also we can extract the tar file from the source directly into the destination.





