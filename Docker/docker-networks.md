# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker Commands

## DOCKER NETWORKS:

- Docker networks are virtual networks that allow containers to communicate with each other and the host system.
  They are created and managed by the Docker engine and can be used to isolate containers from each other or to allow them to communicate.

docker network create: Create a new network

docker network inspect: Display detailed information on one or more networks

docker network ls: List all networks

docker network rm: Remove one or more networks

docker network connect: Connect a container to a network

docker network disconnect: Disconnect a container from a network

Here is an example usage of these commands:

    # Create a new network called "my-network"
    docker network create my-network

    # List all networks
    docker network ls

    # Inspect the network "my-network"
    docker network inspect my-network

    # Connect a running container to the network "my-network"
    docker network connect my-network my-container

    # Disconnect a container from the network "my-network"
    docker network disconnect my-network my-container

    # Remove the network "my-network"
    docker network rm my-network

## Bridge Network

- A bridge network is a virtual network created by Docker that allows containers to communicate with each other and the host system. It is created by default when you install Docker.

Create a bridge network:

    docker network create --driver bridge my-network

Connect a container to a bridge network:

    docker run -it -d --network my-network --name my-container my-image

Disconnect a container from a bridge network:

    docker run -it -d --network my-network --name my-container my-image

## Host Network

- A host network is a network that is created by Docker and shares the host system's network stack. Containers connected to a host network can communicate with the host system and other containers on the same host, but are isolated from other networks.

Create a host network:

    docker network create --driver host my-network

Connect a container to a host network:

    docker run -it -d --network my-network --name my-container my-image

Disconnect a container from a host network:

    docker run -it -d --network my-network --name my-container my-image

## Overlay Network

- An overlay network allows containers on different Docker hosts to communicate with each other. It is created using the Docker Swarm mode and allows containers to communicate across multiple Docker hosts.

Create a overlay network:

    docker network create --driver overlay my-network

Connect a container to a overlay network:

    docker run -it -d --network my-network --name my-container my-image

Disconnect a container from a overlay network:

    docker run -it -d --network my-network --name my-container my-image

## None Network

- A none network is a special network type that removes all network access from a container. It is used to create containers that do not have any network connectivity.

Create a none network:

    docker network create --driver none my-network

Connect a container to a none network:

    docker run -it -d --network my-network --name my-container my-image

Disconnect a container from a none network:

    docker run -it -d --network my-network --name my-container my-image
