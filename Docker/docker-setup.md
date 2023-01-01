# **WELCOME TO THE DOCKER COMMANDS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)

    sudo apt install docker.io

    sudo docker pull ubuntu
    sudo docker images

    sudo docker run -it -d ubuntu
    sudo docker ps

    sudo docker run -it -d --name yccontainer1 ubuntu
    sudo docker run -it -d --name yccontainer2 -p 80:80 ubuntu
    sudo docker exec -ti yccontainer2 bash
    sudo ls
