# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker Swarm

## DOCKER SWARM:

- Docker Swarm is a tool used to create and manage a cluster of Docker nodes as a single virtual system.

- It allows you to turn a group of Docker engines into a single, virtual Docker engine.

## DOCKER SWARM COMMANDS INFO:

docker swarm init - initializes a Docker Swarm as a single-node swarm

docker swarm join - joins a Docker Swarm as a worker or manager node

docker swarm leave - leaves a Docker Swarm as a worker or manager node

docker node ls - lists all nodes in the Swarm

docker node promote - promotes a worker node to a manager node

docker node demote - demotes a manager node to a worker node

docker service create - creates a new service in the Swarm

docker service ls - lists all services in the Swarm

docker service update - updates an existing service in the Swarm

docker service scale - scales the number of replicas for a
service in the Swarm

docker service rm - removes a service from the Swarm

docker stack deploy - deploys a Docker Compose file to the Swarm

docker stack ls - lists all stacks in the Swarm

docker stack rm - removes a stack from the Swarm

## DOCKER SWARM COMMANDS:

This command initializes a Swarm cluster on the current host.

    docker swarm init

This command adds a new node to the Swarm cluster as a worker. The TOKEN and MANAGER_IP:PORT are provided by the Swarm manager.

    docker swarm join --token <TOKEN> <MANAGER_IP>:<PORT>

This command lists all the nodes in the Swarm cluster.

    docker node ls

This command creates a new service in the Swarm cluster with the specified name, number of replicas, and image.

    docker service create --name <SERVICE_NAME> --replicas <REPLICAS> <IMAGE>

This command lists all the services in the Swarm cluster.

    docker service ls

This command displays detailed information about the specified service.

    docker service inspect <SERVICE_NAME>

This command scales the specified service to the desired number of replicas.

    docker service scale <SERVICE_NAME>=<REPLICAS>

This command updates the image of the specified service.

    docker service update --image <IMAGE> <SERVICE_NAME>

This command removes the specified service from the Swarm cluster.

    docker service rm <SERVICE_NAME>

This command removes the current node from the Swarm cluster.

    docker swarm leave
