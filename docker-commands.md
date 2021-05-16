# Docker commands

[Official Docs](https://docs.docker.com/engine/reference/run/)

### Docker Run

When running an image, Docker will first look for cacched images.

If the image you're looking for is not there, it will look for it on Docker Hub. This execution will take a bit longer than running the cached image.

Run image
```
> docker run hello-world

Hello from Docker! // prints a default command to run for this image
... and a bunch of other information

```
Another way of running the image is to use context (container prefix).

```
> docker run container hello-world

Hello from Docker!

```

Run image and pass default command (if image allows for that)

1) Instruct container to print something to the console

```
> docker container run busybox echo "Hello World"
Hello World

```
2) Instruct container to print a list of folders

```
> docker container run busybox ls
 bin
 etc
 home
 root
 sys
 temp
 usr
...
```
#
### Docker ls

Print all running containers

```
> docker container ls
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

Print all containers ever used

```
> docker container ls -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
ceab12314dff   busybox    "ls"      x ago     Excited (0)       randomly_generated_name (or our custom one)
```
#

### Docker Create & Start

Docker Run can be split into two commands:
* Create
* Start



In short,
**Docker Run = Docker Start + Docker Run**
#

### Docker build

Build a container from Docker file (default one)

```
> docker build . 
digest sha2256 hj123jkh142j14hjk15gk1
steps 1/x
...
Successfully built 21dlawkjklbkhf (container id)
```

Build a container from a custom docker file (e.g. Dockerfile.dev)

```
> docker build -f Dockerfile.dev .
digest sha2256 hj123jkh142j14hjk15gk1
steps 1/x
...
Successfully built 21dlawkjklbkhf (container id)
```

To run container we use docker run command

```docker run 21dlawkjklbkhf```
#

### Docker System Prune

Remove all unused images.
