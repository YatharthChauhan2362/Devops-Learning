# **WELCOME TO THE DEVOPS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          Jenkins Installation

## JENKINS INSTALLATION COMMANDS:

To install Jenkins on a Linux machine, you can follow these steps:

Java jdk must be required:

    sudo apt install openjdk-11-jdk

Download the Jenkins repository signing key:

    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -

Add the Jenkins repository to the list of repositories on your machine:

    echo deb https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list

Update the package manager's local package cache:

    sudo apt-get update

Install Jenkins:

    sudo apt-get install jenkins

This will install the latest version of Jenkins and its dependencies on your machine.

After installation, the Jenkins service will start automatically. To verify that Jenkins has been installed successfully, you can check the status of the service:

    systemctl status jenkins

This should show that the Jenkins service is running.

You can then access the Jenkins web interface by opening a web browser and navigating to
http://localhost:8080.
