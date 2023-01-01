# **WELCOME TO THE NGINX DOCKER**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker File

## Docker File

A Dockerfile is a text file that contains all the commands a user could call on the command line to assemble an image.

When you run docker build, the Docker engine takes the instructions in the Dockerfile and creates a new image.

## Dockerfile Commands

FROM: Specifies the base image that the image should be built on top of.

RUN: Runs a command and commits the result as a new layer in the image.

CMD: Specifies the default command that should be run when a container is started from the image.

ENV: Sets an environment variable in the image.

COPY: Copies files or directories from the host file system into the image.

ADD: Similar to COPY, but also supports fetching files from the internet and unpacking them.

EXPOSE: Exposes a port to be mapped by the -p flag when starting a container.

WORKDIR: Sets the working directory for subsequent RUN, CMD, and ENTRYPOINT commands.

ENTRYPOINT: Specifies the command that should be run when a container is started from the image, similar to CMD, but the command cannot be overridden.

USER: Sets the user that should be used for subsequent commands.

VOLUME: Creates a mount point for external data volumes.

For an Example:

    FROM ubuntu:18.04

    RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip

    COPY requirements.txt .
    RUN pip3 install -r requirements.txt

    COPY app.py .

    EXPOSE 8000

    CMD ["python3", "app.py"]

This Dockerfile starts with the ubuntu:18.04 base image and installs python3 and python3-pip.

It then copies a file called requirements.txt from the host into the image and installs the packages listed in the file using pip3.

It copies the file app.py into the image and exposes port 8000.

The default command that will be run when a container is started from this image is python3 app.py, which will start the Python app.
