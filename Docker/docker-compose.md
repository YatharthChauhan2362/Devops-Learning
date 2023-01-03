# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Docker Compose

## DOCKER COMPOSE:

Docker Compose is a tool for defining and running multi-container Docker applications.

It allows users to define a set of related services, including their dependencies and configurations, in a single YAML file.

## INSTALL DOCKER COMPOSE:

Download the current stable release of Docker Compose:

    sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

Apply executable permissions to the binary:

    sudo chmod +x /usr/local/bin/docker-compose

Test the installation:

    docker-compose --version

## DOCKER COMPOSE COMMANDS:

This command is used to build the images specified in the docker-compose.yml file.

    docker-compose build:

This command is used to bring up the containers specified in the docker-compose.yml file.

    docker-compose up:

This command is used to stop and remove the containers and networks created by the docker-compose up command.

    docker-compose down:

This command is used to list the containers that are running in the docker-compose environment.

    docker-compose ps:

This command is used to view the logs of the containers specified in the docker-compose.yml file.

    docker-compose logs:

This command is used to execute a command inside a container specified in the docker-compose.yml file.

    docker-compose exec:

This command is used to stop the containers specified in the docker-compose.yml file.

    docker-compose stop:

This command is used to start the containers specified in the docker-compose.yml file.

    docker-compose start:

This command is used to pause the containers specified in the docker-compose.yml file.

    docker-compose pause:

This command is used to unpause the containers specified in the docker-compose.yml file.

    docker-compose unpause:
