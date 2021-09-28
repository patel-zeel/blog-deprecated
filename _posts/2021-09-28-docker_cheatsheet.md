---
toc: true
layout: post
description: Most used command while working with Docker 
categories: [markdown]
title: Docker Cheatsheet
---
# Docker Cheatsheet

* Open a running container's terminal.
```bash
$ #docker exec -it <container-name> bash
$ docker exec -it aaai bash # -it stands for interactive
```

* Execute any command on a running container without opening a shell in container.
```bash
$ # docker exec -it <container-name> <command>
$ docker exec -it aaai jupyter notebook list
```

* Check containers
```bash
$ docker ps # shows running containers
$ docker ps -a # shows all containers
```

* Start or stop a container (default script will be executed with this).
```bash
$ # docker start <container-name>
$ docker start aaai # This will start the jupyter notebook server along with the container
$ # docker stop <container-name> 
$ docker stop aaai
```

* Delete a container.
```bash
$ # docker rm <container-name>
$ docker rm aaai
```

* Check server logs (including shell commands output)
```bash
$ # docker logs <container-name>
$ docker logs aaai
```

* Create a new container from an image
  1. -v: for telling docker to use a shared directory between host and container
  2. -p \<host-port\>\<container-port\>: is to use port forwarding, an application running on \<container-port\> can be accessed only with \<host-port\> in host.
  3. --name generates a name for the container for easy reference in other commands
  4. --gpus all tells docker to use all GPUs available on host
  5. -m Restricts RAM usage
  
```bash
$ docker create tensorflow/tensorflow:2.4.0-gpu-jupyter # Creates new container with random name and other default params
$ # or
$ docker create \
-v \path_in_host:\path_in_container \
-p9000:8888 \
--name aaai \
--gpus all \
-m 100g \
tensorflow/tensorflow:2.4.0-gpu-jupyter
```

* Update any of the above configurations.
```bash
$ # change RAM limit to the "aaai" container
$ docker update -m 50g aaai
```
  
* Check images currently present within docker
```bash
$ docker images
```
  
* Download/Pull a docker image from Docker Hub or respective websites.
```bash
$ # docker pull <image-name>:<tag>
$ docker pull tensorflow/tensorflow:2.4.0-gpu-jupyter
```