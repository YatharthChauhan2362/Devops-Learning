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

#TASK-1

    sudo apt install docker.io

    sudo docker pull ubuntu
    sudo docker images

    sudo docker run -it -d ubuntu
    sudo docker ps

    sudo docker run -it -d --name yccontainer1 ubuntu
    sudo docker run -it -d --name yccontainer2 -p 80:80 ubuntu
    sudo docker exec -ti yccontainer2 bash
    sudo ls
