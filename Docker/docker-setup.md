# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)

## Ccommon Docker commands:

    docker build - Build an image from a Dockerfile
    docker run - Run a command in a new container
    docker start - Start one or more stopped containers
    docker stop - Stop one or more running containers
    docker rm - Remove one or more containers
    docker rmi - Remove one or more images
    docker ps - List containers
    docker images - List images
    docker exec - Run a command in a running container
    docker logs - Fetch the logs of a container

# docker installation

    apt install docker.io

# docker build

- The docker build command is used to build a Docker image from a Dockerfile. A Dockerfile is a text file that contains the instructions for building a Docker image.
  It specifies the base image to use, the packages to install, and any other configuration or dependencies that are required.

      docker build [OPTIONS] PATH | URL | -

The PATH argument specifies the location of the directory that contains the Dockerfile. You can either provide the path to the directory on the local filesystem, or you can specify a URL to a Git repository that contains the Dockerfile.

to build a Docker image from a Dockerfile in the current directory,

    docker build .

To build a Docker image from a Dockerfile in a different directory, you would run:

    docker build /path/to/directory

You can use various options with the docker build command to modify its behavior.

For example, you can use the -t option to specify a name and optionally a tag for the image in the name:tag format.

    docker build -t my-image:latest .

You can use the --build-arg option to pass build-time variables to the Docker build process. These variables can be used in the Dockerfile to parameterize the build process.

    docker build --build-arg MY_VAR=123 .

# docker run

The docker run command is used to run a Docker container. The -it and -d options are commonly used with docker run.

The -it option stands for "interactive" and "tty", and it allows you to run the container in an interactive shell.
This is useful if you want to run a command-line application in a container and interact with it in real-time.

The -d option stands for "detached", and it runs the container in the background as a daemon.
This is useful if you want to run a container and leave it running in the background.

    docker run -it -d my-image

# docker start

The docker start command is used to start a stopped Docker container. It is used to resume the execution of a container that has been previously stopped.

    docker start [OPTIONS] CONTAINER [CONTAINER...]

To start a container, you need to provide the container ID or name as an argument.

For example, to start a container with the ID 7e38f2f1c567, you would run:

    docker start 7e38f2f1c567

You can also start multiple containers at the same time by providing multiple container IDs or names as arguments.

    docker start 7e38f2f1c567 9b1702f8e492

# docker stop

# docker rm

# docker rmi

# docker ps

# docker images

The docker images command is used to list the images that are available on a Docker host. It shows the repository, tag, and ID of each image.

Here is the basic syntax for the docker images command:

    docker images [OPTIONS] [REPOSITORY[:TAG]]

For example, to list all images that are stored locally on the host, you would run:

    docker images

To list only the images from the alpine repository, you would run:

    docker images ubuntu

# docker exec

The docker exec command is used to run a command in a running Docker container. The -ti options are commonly used with docker exec.

The -t option stands for "tty", and it allocates a pseudo-tty for the container. This is useful if you want to run an interactive command that requires a tty, such as a shell.

The -i option stands for "interactive", and it allows you to interact with the container in real-time. This is useful if you want to run a command and receive output from it in real-time.

    docker exec -ti my-container bash

    docker exec my-container cat /etc/hosts

# docker logs

# docker pull

The docker pull command is used to pull or download a Docker image from a registry. You can use it to pull images from the default Docker Hub registry or from a private registry.

Here is the basic syntax for docker pull:

    docker pull [OPTIONS] NAME[:TAG|@DIGEST]

For example, to pull the latest version of the alpine image from the Docker Hub registry, you would run:

     docker pull ubuntu

# docker ps

The docker ps command is used to list the running Docker containers on a host. It shows the container ID, image name, command being run, and the status of each container.

Syntax:

    docker ps [OPTIONS]

By default, docker ps will list all running containers on the host. If you want to see all containers (both running and stopped), you can use the -a flag.

    docker ps

To list all containers (both running and stopped), you would run:

    docker ps -a

You can also use the -f option to filter the list of containers by providing a filter expression.

For example, to list all containers that are using the alpine image, you would run:

    docker ps -f "image=alpine"

# -p

The -p option is used with the docker run command to publish a container's port to the host. It maps a container port to a host port, so that traffic to the host port is forwarded to the container port.

The -p option takes a value in the form HOST_PORT:CONTAINER_PORT.

For example, the value 80:80 maps the host port 80 to the container port 80.

    docker run -p 80:80 my-image

You can specify multiple -p options to publish multiple ports.

For example:

    docker run -p 80:80 -p 443:443 my-image
