# Docker commands

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

1) Instruct container print something to the console

```
> docker container run busybox echo "Hello World"
Hello World

```
2)Instruct container to print a list of folders

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
