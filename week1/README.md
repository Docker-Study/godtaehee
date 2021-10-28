# WEEK 1

## Why we use docker?

- We can install any program easily using docker

### Installing Redis without using a docker

```shell
wget http://download.redis.io/releases/redis-6.0.5.tar.gz
tar xzf redis-6.0.5.tar.gz
cd redis-6.0.5
make
```

Is it going well? If it goes well, do what you've been doing.

If `wget` is not installed in your device, we must install `wget` command

Before we install any application, we must pre-install other thing

That's why we use docker

If we use docker, we don't need to pre-install other thing no more

### Installing Redis using a docker

```shell
docker run -it redis
```

You can simply download above command.

Of course, you can download Redis without using a docker.

But, using a docker, Redis can be installed more easily.

![Screen Shot 2021-10-26 at 11 02 04 PM](https://user-images.githubusercontent.com/44861205/138894975-3ada5259-aa47-4ec2-b083-568b2a01bd3c.png)

## What is a docker?

> Docker is an open platform for developing, shipping, and running applications.

Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. 


## The Docker Dashboard

Docker Dashboard gives you a quick view of  the containers running on your machine.

It gives you quick access to container logs, lets you get a shell inside the container, and lets you easily manage container lifecycle(stop, remove, etc..)

![Screen Shot 2021-10-27 at 9 18 56 PM](https://user-images.githubusercontent.com/44861205/139064066-0abc4f1b-c440-4587-8ab8-a64df70289e7.png)

## What is a container?

A container is a sandboxed process on your machine that is isolated from all other processes on the host machine.

That isolation leverages [kernel namespaces and croups](https://medium.com/@saschagrunert/demystifying-containers-part-i-kernel-space-2c53d6979504), feature that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use.

> We can learn detail thing about docker container using `chroot` command 
> After you use 'chroot' command, or you're already good at using 'chroot', 
> You can understand docker container easily [Link](https://www.44bits.io/ko/post/change-root-directory-by-using-chroot)

## What is a container image?

When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. Since the image contains the container’s filesystem, it must contain everything needed to run an application - all dependencies, configuration, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.


## Docker Container Lifecycle

![Screen Shot 2021-10-28 at 7 38 41 PM](https://user-images.githubusercontent.com/44861205/139239954-384fb9d6-37ac-42d7-8381-e89372d63798.png)


### docker create

#### Usage

```shell
docker create <Image Name>
```

#### Description

Create a new container

You will get container id After this command is executed


### docker start

#### Usage

```shell
docker start <Container Id/Name>
```

#### Description

Run a command in a new container

### docker run

#### Usage

```shell
docker run <Image Name>
```

#### Description

`docker run` can be divided two command.

> `docker run <Image Name>` = `docker create <Image Name>` + `docker start <Container Id/Name>` 

### docker stop VS docker kill

`docker stop` is more graceful than `docker kill`

See below official docs' description about `docker stop`


> The main process inside the container will receive SIGTERM, and after a grace period, SIGKILL. The first signal can be changed with the STOPSIGNAL instruction in the container’s Dockerfile, or the --stop-signal option to docker run.

In contrast, You can see official docs' description about `docker kill`

> The docker kill subcommand kills one or more containers. The main process inside the container is sent SIGKILL signal (default)


### docker rm <Id/Name>

> [!IMPORTANT] You can remove container After container is stopped


#### Remove container

If you want to remove all container, Use **docker rm `docker ps -a -q`**

You can also use `docker container prune`

#### Remove image

> [!IMPORTANT] You can remove image After container is stopped. For example, If you create A container using B Image, B Image can't be removed Until A container is stopped. In other words, Container and Image have dependency each other

You can remove image `docker rmi <ImageId>`

You can also use `docker image rm`

### Remove container, image, network at once

Use `docker system prune`

When you use docker for a long time, there is possibility which useless docker's file occupies capacity in your hdd

So I suggest you that you use `docker system prune` command when you don't use docker anymore

This command don't remove container which is been executed

### docker exec <Container Id>

You can send command to container which is already executed



