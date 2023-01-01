# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker Commands

## DOCKER NETWORKS:

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
