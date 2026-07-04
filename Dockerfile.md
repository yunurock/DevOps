# Docker File 
A Dockerfile is a text file that contains instructions to build a Docker image automatically.

## Why use a Dockerfile?
Instead of manually installing software every time you create a container, you write the steps once in a Dockerfile, and Docker builds the image for you.

Set of DockerFile Instructions:
===============================
FROM: where to download the base image.-
MAINTAINER: Non executable instruction used to indicate the author of DockerFile.
COPY: Copy file from docker host to image.
ADD: It copy the file from source to destination and also extracts the file.
CMD: It specifies the intended command for the image.
ENTRYPOINT: when the container is up,entry point is the starting of execution.
ENV: This instruction can be used to set the env variables in the container.
EXPOSE: expose a specified port.
RUN: This instruction is used to execute a command on top of an existing layer.
USER: This is used to set the username.
VOLUME: Volume instruction is used to enable access to a location.
WORKDIR: To change the directory.
ONBUILD: It will add a trigger instruction.
