# Docker-Commands
Basic docker commands


$docker                       			// show commands          
$docker version                         // show version
$docker info                            // show number of containers

$docker ps                              // show all running containers
$docker ps -a                           // show all containers

$docker container stop [id]             // stop container by id
$docker stop $(docker ps -a -q)         // stop all
$docker container remove [id]           // remove container by id
$docker container remove -f [id]        // force remove container by id
$docker rm $(docker ps -a -q)           // remove all

$docker container logs [name]           // get logs from a container
$docker container top [name]            // get info from a container

$docker image ls                        // list images on the system
$docker pull [image-name]               // pull an image
$docker image rm [image-name]           // remove an image
$docker image rm $(docker images -a)    // remove all images

$docker container state [name]          // get performance stats
$docker container inspect [name]        // inspect container


$docker container port [name]
$docker network -ls
$docker nework create [network-name]
$docker container run -d --name [name] --network [network]
$docker network connect [network-name] [container-name]     // connect to another container
$docker network disconnect [network-name] [container-name]  // disconnect from another container
// docker uses bridged network driver by default

$docker image tag [tag] [image-name] repo/gwyndon                // tag an image for docker hub

$docker login                                               // login to docker hub
$docker image push repo/[image-name]



// create and run a container in interactive mode
$docker run -it -p 80:80 ubuntu 
$docker run -it -p 198.27.107.205:80:80 ubuntu  

// create and run a container as a background process
$docker run -it -d 80:80 ubuntu
$docker run -it -d 198.27.107.205:80:80 ubuntu 

// access a container
$docker container exec -it [name] /bin/bash

// naming containers
$docker container run -d -p --name [name] ubuntu




docker run -it -p 198.27.107.205:80:80 -p 198.27.107.205:443:443 ubuntu

$docker container inspect --format `{{.NetworkSettings.IPAddress}}` [name]
