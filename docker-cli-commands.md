# Docker CLI commands

[Official Docs](https://docs.docker.com/engine/reference/run/)

List out all commands:
```bash
> docker help
```

### Build, Create, Start, Run

Run container
```bash
> docker container run hello-world 
> docker container run f1234h27g5

# docker (optional) container <action> <container-name> or <container-id>
```

Pass parameter when running container:
```bash
> docker container run busybox ls
```

Run a docker container and go inside it
```bash
> docker run -it 
```

**Docker Run = Docker Create + Docker Start**


List out all running containers:
```bash
> docker container ps # or docker container ls

CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

List out all containers (even inactive):
```bash
> docker container ls -a

CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
ceab12314dff   busybox    "ls"      x ago     Excited (0)       randomly_generated_name (or our custom one)
```

Create a container without running:
```bash
> docker container create hello-world
```
Run created container

```bash
> docker container start -a <container-name> or <container-id>
# -a prints commands in the terminal
```

Remove all unused images:
```bash
> docker system prune --all
```

Log all activities within a container
```bash
> docker container logs
```
Stop the container when possible
```bash
> docker container stop <container-name> or <container-id>
```
Terminate the container immediately:
```bash
> docker container kill <container-name> or <container-id>
```

Tag the image upon building
```bash
> docker build . -t awesome
```

Remove the container
```bash
> docker remove container <container-name> or <container-id>
```



Docker build
Docker build is used to construct a Docker image from a Dockerfile. 

```
> docker build . 
digest sha2256 hj123jkh142j14hjk15gk1
steps 1/x
...
Successfully built 21dlawkjklbkhf <container-id>
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

Delete all containers
```bash
> docker system prune --all # remove cache
```


Tag the image upon building
```bash
> docker build . -t awesome
```

Remove the container
```bash
> docker remove container name or SHA
```

Docker push / docker pull to push or pull containers from docker hub

Get cpu and RAM and system info of container

```bash
> docker container inspect
```

Run a command within a container
```bash
> docker container exec -it <container-id> redis-cli

-it goes inside the container (interact)

1237.0.0.1:6379> // inside redis cli
```

SSH into a container:
```bash
> docker exec -it <id> sh
# type exit to *exit*
```
Start a container with a shell:
```bash
> docker container run -it busybox sh
# goes inside CMD.
```
