# **WELCOME TO THE DEVOPS**

    AUTHOR:         Yatharth Chauhan  (Github: YatharthChauhan2362)
    TOPIC:          ELK Installation

## ELK INSTALLATION

## Install Dependencies

Install Java

    apt-get install -y openjdk-11-jdk
    
## Install Nginx

Nginx works as a web server and proxy server. It’s used to configure password-controlled access to the Kibana dashboard.

    apt-get install -y nginx

## Add Elastic Repository

Elastic repositories enable access to all the open-source software in the ELK stack. To add them, start by importing the GPG key.

    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
    
install the apt-transport-https package:

    sudo apt-get install apt-transport-https
    
4Add the Elastic repository to your system’s repository list:

    echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee –a /etc/apt/sources.list.d/elastic-7.x.list\
    
## Install Elasticsearch

Prior to installing Elasticsearch, update the repositories by entering:

    sudo apt-get update
    
Install Elasticsearch with the following command:

    sudo apt-get install elasticsearch
    
    sudo apt install kibana
    
    sudo apt install logstash
    
    sudo apt install filebeat


server {
       listen 80;

       server_name 192.168.10.129;

       auth basic "Restricted Access";
       auth_basic_user_file /etc/nginx/htpasswd.users;

       location / {
              proxy_pass http://localhost:5601>;
              proxy_http_version 1.1;
              proxy_set_header Upgrade $http_upgrade;
              proxy_set_header Connection 'upgrade';
              proxy_set_header Host $host;
              proxy_cache_bypass $http_upgrade;
       }
}

    
