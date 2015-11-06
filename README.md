# Docker Message-Broker Images

This project holds Docker builds for various message-brokers with various versions. The project uses the docker-maven-plugin
internally to build the images. You can build the images locally on the Dockerhost with

````
mvn clean package docker:build
````

By default the environment variable `DOCKER_HOST` is evaluated for connecting to the Docker deamon on your host. Use the
docker-maven-plugin configuration settings for other connection parameters to the Docker daemon.

You can restrict the images to build by selecting the maven sub modules

````
mvn -pl activemq clean package docker:build
````
 
## Servers

Currently we have the following servers 

* Apache ActiveMQ: 5.11, 5.12

All server images are pushed to [hub.docker.io](https://registry.hub.docker.com/repos/consol/) and can be faved there ;-)