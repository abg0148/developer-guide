Docker

platform to run distributed applications

it allows you to run containers..

containers are like virtual environment, to be accurate sandboxed. a container is a sandboxed application that runs an application and dependencies.

advantage with containers is since they are sandboxed conflicts in dependencies is avoided. also deployment can be simplified by doing all the installation and configurations beforehand.

docker has three key components

docker engine
docker client
docker registry

engine provides a way to start the containers

client allows to communicate with the engine

registry hosts the docker image

Launching Containers

1_ running a container

with docker, all containers start based on a docker image, this image contains everything required to launch the process. we don't need to provide any configuration or dependencies.

to start the container you need to build your custom docker image or use an existing image created by docker community.

to find the existing docker images, use:

registry.hub.docker.com or,
docker search <image-name>

when you search this way, you will find many variations of an image. its recommended to use the official image or the one with most stars. after identifying the image you want to run, launch it using 

docker run <image-name>

all containers are given a name and id for use in other docker commands, a name can be provided to a container during launching using 

docker run --name <name> <image-name>

for running the command in background use

docker run -d <image-name>

2_ listing running containers

docker ps

this command can be used to display friendly name and id of the container too, which can help find other info about containers.

to get more details about running container use

docker inspect <name|container-id>

also,

docker logs <name|container-id>

will display the messages that container has written to standard out and standard error.

3_ binding ports

we have discussed that containers are sandboxed from other containers. if we need to make any service accessible externally, then we need to expose a port to be mapped to the host machine. once this mapping is done, we will be able to access the service as if the process was running on the host OS itself instead of the container. 

when starting the container, we can define the ports that we want to bind using

-p <host-port>:<container-port>

















