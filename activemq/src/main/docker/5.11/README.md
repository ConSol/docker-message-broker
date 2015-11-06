## ActiveMQ 5.11

A simple docker build for installing a vanilla ActiveMQ 5.11 below
*/opt/apache-activemq*. It comes out of the box and is intended for use in
integration tests

This image will enable a Jolokia agent during startup which can be reached
by default within the container at port 8778.

The environment variable `$JOLOKIA_OFF` can be set so that the agent won't start.

More information about Jolokia configuration options can be found at
[jolokia/java-jolokia](https://registry.hub.docker.com/u/jolokia/java-jolokia)

Features:

* ActiveMQ Version: **5.11.2**
* Java Version: **OpenJDK 1.7.0_79 (7u79-2.5.5-1~deb8u)** (base image: *jolokia/java-jolokia:7*)
* Port: **8161**, **61616**, **61613**, **1883**, **61614**, **5672**
* Command: `/opt/apache-activemq/bin/activemq console` which runs the activemq broker