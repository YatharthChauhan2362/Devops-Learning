# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker Commands

## COMMON DOCKER COMMANDS IN LINUX:

    docker build - Build an image from a Dockerfile
    docker run - Run a command in a new container
    docker start - Start one or more stopped containers
    docker stop - Stop one or more running containers
    docker kill - To kill a running Docker container
    docker restart - restart a Docker container
    docker rm - Remove one or more containers
    docker rmi - Remove one or more images
    docker ps - List containers
    docker images - List images
    docker exec - Run a command in a running container
    docker logs - Fetch the logs of a container
    docker login - log in to a Docker registry
    docker push - upload a Docker image to a registry
    docker pull - download a Docker image from a registry
    docker kill - To kill a running Docker container
    docker commit - To save the changes and create a new image
    docker tag - To add a tag to a Docker image in a registry.

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

# docker kill

To kill a running Docker container, you can use the docker kill command followed by the name or ID of the container.

For example:

    $ docker kill my_container

This will send a SIGKILL signal to the process running in the container, which will cause the process to terminate immediately.

# docker restart

To restart a Docker container, you can use the docker restart command followed by the name or ID of the container.

For example:

    $ docker restart my_container

This command stops and then starts the container. When you restart a container, all of its processes are terminated, and then the processes are started again.

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

    docker images my-image

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

# docker login

The docker login command is used to log in to a Docker registry. A registry is a repository for Docker images, and it allows you to share your images with others or to use images created by others.

The basic syntax for docker login is:

    $ docker login [OPTIONS] [SERVER]

Here is an example of how to use docker login:

    $ docker login

This command prompts you for your Docker ID and password, and then logs you in to the default registry (Docker Hub).

You can also specify the registry URL as the "SERVER" parameter if you want to log in to a different registry.

For example:

    $ docker login my_registry

--password to specify the password on the command line (instead of being prompted for it)
--username to specify the username on the command line
--help to view a list of all available options.

Keep in mind that you need to be logged in to a registry before you can push an image to the registry or pull an image from the registry.

# docker push

The docker push command is used to upload a Docker image to a registry. A registry is a repository for Docker images, and it allows you to share your images with others or to use images created by others.

The basic syntax for docker push is:

    $ docker push [OPTIONS] NAME[:TAG]

Here is an example of how to use docker push:

    $ docker push my_image:v1

This command pushes the image "my_image:v1" to the default registry (Docker Hub). If you are using a different registry, you can specify the registry URL as part of the image name.

For example:

    $ docker push my_registry/my_image:v1

--disable-content-trust to disable image signing
--dry-run to perform a trial run without actually pushing the image
--help to view a list of all available options.

# docker pull

The docker pull command is used to pull or download a Docker image from a registry. You can use it to pull images from the default Docker Hub registry or from a private registry.

Here is the basic syntax for docker pull:

    docker pull [OPTIONS] NAME[:TAG|@DIGEST]

For example, to pull the latest version of the alpine image from the Docker Hub registry, you would run:

     docker pull my-image

# docker commit

The docker commit command is used to create a new Docker image from a container's changes. When you make changes to a container, such as installing software, modifying configuration files, or writing new files, those changes are not saved to the original image from which the container was created.

To save the changes and create a new image, you can use docker commit.

syntax:

    $ docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]

For an Example:

    $ docker commit my_container my_image:v1

This command creates a new image called "my_image" with the tag "v1" based on the changes made to the container "my_container".
The new image will include all of the changes made to the container, such as installed software, modified configuration files, and new files.

# docker tag

The docker tag command is used to add a tag to a Docker image in a registry.

Tagging an image is useful for organizing images in a registry, and for referring to specific versions of an image when deploying applications.

Syntax:

    $ docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]

Here is an example of how to use docker tag:

    $ docker tag my_image:v1 my_image:latest

This command adds the tag "latest" to the image "my_image" with the tag "v1".

You can also use docker tag to create a new image in a different registry.

For example:

    $ docker tag my_image:v1 my_registry/my_image:v1

This command creates a new image called "my_image:v1" in the registry "my_registry", based on the image "my_image:v1" in the local image store.
