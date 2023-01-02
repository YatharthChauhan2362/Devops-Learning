# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          NGINX Docker

## NGINX:

- NGINX is a popular open-source web server that can be used with Docker to run web applications in a containerized environment.

- To use NGINX with Docker, you will need to follow these steps:

1. Install Docker on your host machine. If you don't already have Docker installed, you can download it from the Docker website or use a package manager to install it.

2. Pull the NGINX Docker image from a registry such as Docker Hub. You can do this using the docker pull command.

For example:

    docker pull nginx

3. Start a new NGINX container using the docker run command.

For example:

    docker run --name my-nginx -p 80:80 nginx

This will start a new NGINX container with the name "my-nginx", and bind the container's port 80 to the host's port 80.
This means that you will be able to access the NGINX server by visiting http://localhost in your web browser.

4.  (Optional) If you want to customize the NGINX configuration, you can mount a custom configuration file into the container using the -v option.

For example:

    docker run --name my-nginx -p 80:80 -v /path/to/nginx.conf:/etc/nginx/nginx.conf nginx

This will use the configuration file at /path/to/nginx.conf on the host as the NGINX configuration file inside the container.

That's it! You should now have NGINX running inside a Docker container.
You can then deploy your web application in the container and access it through the NGINX server.

## NGINX COMMANDS:

This command will test the NGINX configuration file for syntax errors.

    nginx -t:

This command will reload the NGINX configuration file. This can be useful if you have made changes to the configuration and want to apply them without restarting the server.

    nginx -s reload:

This command will stop the NGINX server.

    nginx -s stop:

This command will start the NGINX server.

    nginx:

This command will display the version of NGINX and the options that were compiled in.

    nginx -V:

This command will display a list of available options and arguments for the nginx command.

    nginx -h:

This command will start the NGINX server using the configuration file at the specified path.

    nginx -c /path/to/nginx.conf:
