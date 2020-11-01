├── config<br />
│   ├── LEMP<br />
│   │   ├── db<br />
│   │   │   └── my.cnf<br />
│   │   ├── nginx<br />
│   │   │   ├── conf.d<br />
│   │   │   │   ├── php.conf<br />
│   │   │   │   └── phpmyadmin.conf<br />
│   │   │   └── www<br />
│   │   │       └── index.php<br />
│   │   └── php<br />
│   │       └── Dockerfile<br />
│   └── Other<br />
│       └── vidoes<br />
├── LEMP<br />
│   ├── docker-compose.yml<br />
│   └── .env<br />
├── Other<br />
│   ├── docker-compose.yml<br />
│   └── .env<br />
├── README.md<br />
└── services<br />
    ├── docker-compose.yml<br />
    └── .env<br />

# Serivces
- Portainer ce
- Watchtower
- nbr23/youtube-dl-server
- Nginx
- MariaDB
- PHP and MYPHPAdmin

This will be a current running setup of my server that will change as I develop things and add to the server.  Which means this repo will never be complete and will have only working setup for you to copy.  Meaning I will be constantly updating it when I add services.  

I have split things up into 3 catagories currently.

<b>Development</b> - This will be for any service that I will need for development meaning servers. Examples Nginx, PHP, MariaDB, PHPMyAdmin, Python, MEAN, NodeJS, Etc.<br />
<b>Services</b> - This will be this that are specific to Docker and the server for making it run or for backup services. Examples Portainter, Watchtower, Etc.<br />
<b>Other</b> - is for Other services that do not fall under the current list of services. Example Youtube-dl, etc.<br />

I will be keeping a runing list of links to the github repos, dockhubs, other sites and videos I use to setup my server for reference perposes so you can reference to them or if you would like more background on the service running here.

I have followed a tutorial from Docker for local web development introduction why should you care <a href="https://github.com/jackfusion/server/blob/master/README.md#01-httpstechosteelmepostsdocker-for-local-web-development-introduction-why-should-you-care">1</a> for the LEMP setup a key note on which I did not undersatnd when I did the index.php file is to have $connection = new PDO('[DBMS]:host=[HOST];dbname=demo;charset=utf8', 'root', 'root'); - this is from great help from osteel the writer of the blog.

docker install on Debian <a href="https://github.com/jackfusion/server/blob/master/README.md#02-httpsdocsdockercomengineinstalldebian">2</a> and Install docker compose - <a href="https://github.com/jackfusion/server/blob/master/README.md#03-httpsdocsdockercomcomposeinstall">3</a> for the docker and docker compose install

sudo apt install -y libssl-dev python-dev libffi-dev libc6-dev gcc make python3-pip gnupg2 net-tools apt-transport-https ca-certificates curl gnupg-agent software-properties-common - these are what is recommended by Docker for alpine and install docker engine

Openmediavault 5 (OMV5) Complete Install and Setup including Portainer on PC <a href="https://github.com/jackfusion/server/blob/master/README.md#04-httpswwwyoutubecomwatchva5ckt7pxrny">4</a> for install and setup of Open Media vault not including the OMV extras because they do not include up to date docker install the one for the docker docs dose.


I have been using <a href="https://github.com/jackfusion/server/blob/master/README.md#05-httpswwwsmarthomebeginnercomdocker-home-media-server-2018-basic">5</a> smart home beginners wesite to help with cleaning up my code and expanding on my containers for development.

For each .env file you will edit the file for each stack you create for organization of the conatiners<br />
```
COMPOSE_PROJECT_NAME={LEMP|OTHER|services} # this is to group the different area under each stack<br />
PUID={id} # id command will show you this # for current user example uid=1000(user)
# Main linux user id that will be running server<br />
PGID={id} # id command will show you this # for current user example 994(docker)
# docker group id<br />
TZ={timezone} # the time zone for your area<br />
USERDIR={location to presistate date} # for me this is one the shares on open media vault
# this will be the location of the persistent data for all services running on the server - presistant data is the data 
# that will be saved for configuration files and services
```
###### 01 https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care
###### 02 https://docs.docker.com/engine/install/debian/
###### 03 https://docs.docker.com/compose/install/
###### 04 https://www.youtube.com/watch?v=A5ckT7pxrNY
###### 05 https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/
###### 06 https://hub.docker.com/_/phpmyadmin
###### 07 https://github.com/phpmyadmin/docker
###### 08 https://hub.docker.com/_/mariadb
###### 09 https://github.com/docker-library/mariadb
###### 10 https://hub.docker.com/_/php
###### 11 https://github.com/docker-library/php
###### 12 https://hub.docker.com/_/nginx
###### 13 https://github.com/nginxinc/docker-nginx/
