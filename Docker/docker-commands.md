# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:        Docker Commands

## Common Docker commands:

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

The docker build command is used to build a Docker image from a Dockerfile. A Dockerfile is a text file that contains the instructions for building a Docker image.
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

The docker stop command is used to stop a running Docker container. It is used to stop the execution of a container and release the resources that it is using.

Syntax:

    docker stop [OPTIONS] CONTAINER [CONTAINER...]

To stop a container, you need to provide the container ID or name as an argument.

For example, to stop a container with the ID 7e38f2f1c567, you would run:

    docker stop 7e38f2f1c567

You can also stop multiple containers at the same time by providing multiple container IDs or names as arguments.

    docker stop 7e38f2f1c567 9b1702f8e492

By default, docker stop sends a SIGTERM signal to the main process inside the container, which allows the process to clean up and terminate gracefully.
If the process does not exit within a specified timeout, docker stop will send a SIGKILL signal to force the process to terminate.

You can use the --time option to specify the timeout in seconds.
The default timeout is 10 seconds.

    docker stop --time 20 7e38f2f1c567

# docker rm

The docker rm command is used to remove one or more Docker containers.
It is used to delete the container and release the resources that it is using.

Syntax:

    docker rm [OPTIONS] CONTAINER [CONTAINER...]

To remove a container, you need to provide the container ID or name as an argument.

For example, to remove a container with the ID 7e38f2f1c567, you would run:

    docker rm 7e38f2f1c567

You can also remove multiple containers at the same time by providing multiple container IDs or names as arguments.

    docker rm 7e38f2f1c567 9b1702f8e492

By default, docker rm will only remove stopped containers. If you want to remove a running container, you can use the -f or --force option to force the removal of the container.

    docker rm -f 7e38f2f1c567

If you want to remove all containers, you can use the docker rm command with the -a or --all option.

    docker rm -a

# docker rmi

The docker rmi command is used to remove one or more Docker images.
It is used to delete the image and release the resources that it is using.

Syntax:

    docker rmi [OPTIONS] IMAGE [IMAGE...]

To remove an image, you need to provide the image ID or name as an argument.

For example, to remove an image with the ID 7e38f2f1c567, you would run:

    docker rmi 7e38f2f1c567

You can also remove multiple images at the same time by providing multiple image IDs or names as arguments.

    docker rmi 7e38f2f1c567 9b1702f8e492

By default, docker rmi will only remove images that are not being used by any containers.
If you want to remove an image that is being used by a container, you can use the -f or --force option to force the removal of the image.

    docker rmi -f 7e38f2f1c

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

# docker images

The docker images command is used to list the images that are available on a Docker host. It shows the repository, tag, and ID of each image.

Here is the basic syntax for the docker images command:

    docker images [OPTIONS] [REPOSITORY[:TAG]]

For example, to list all images that are stored locally on the host, you would run:

    docker images

To list only the images from the alpine repository, you would run:

    docker images ubuntu

# docker exec

The docker exec command allows you to run a command in a running Docker container.
This can be useful for debugging or for running scripts or commands inside the container.

Syntax:

    docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

For example, to run the ls command in a container with the ID ee2f8cec8123.

    docker exec ee2f8cec8123 ls

This will run the ls command in the specified container and display the output.

-i option to run the command interactively.
-t option to allocate a pseudo-TTY.
-w option to specify the working directory in which the command should be run.
--user option to specify the user that should be used to run the command.

# docker logs

To view the logs of a Docker container, you can use the docker logs command.
This command allows you to retrieve the logs that are produced by a running container.

Syntax for the docker logs command:

    docker logs [OPTIONS] CONTAINER

For example, to view the logs of a container with the ID ee2f8cec8123, you can run the following command:

    docker logs ee2f8cec8123

There are several options that you can use with docker logs to control the output.

--follow option to continuously stream the logs as they are produced.

--tail option to only show the most recent N lines of the logs.

--since option to only show logs produced since a certain time.

--timestamps option to include timestamps in the output.

# docker pull

The docker pull command is used to pull or download a Docker image from a registry. You can use it to pull images from the default Docker Hub registry or from a private registry.

Here is the basic syntax for docker pull:

    docker pull [OPTIONS] NAME[:TAG|@DIGEST]

For example, to pull the latest version of the alpine image from the Docker Hub registry, you would run:

     docker pull ubuntu

# docker run -p

The -p option is used with the docker run command to publish a container's port to the host. It maps a container port to a host port, so that traffic to the host port is forwarded to the container port.

The -p option takes a value in the form HOST_PORT:CONTAINER_PORT.

For example, the value 80:80 maps the host port 80 to the container port 80.

    docker run -p 80:80 my-image

You can specify multiple -p options to publish multiple ports.

For example:

    docker run -p 80:80 -p 443:443 my-image
