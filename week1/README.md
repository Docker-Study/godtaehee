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



