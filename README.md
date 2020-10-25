├── LEMP <br />
│   ├── config <br />
│   │   ├── db <br />
│   │   │   └── my.cnf <br />
│   │   ├── nginx <br />
│   │   │   ├── conf.d <br />
│   │   │   │   ├── php.conf <br />
│   │   │   │   └── phpmyadmin.conf <br />
│   │   │   └── www <br />
│   │   │       └── index.php <br />
│   │   └── php <br />
│   │       └── Dockerfile <br />
│   ├── docker-compose.yml <br />
|    └── .env <br />
├── Other <br />
│   ├── docker-compose.yml <br />
|    └── .env <br />
└── services <br />
     ├── docker-compose.yml <br />
     └── .env <br />

# Serivces
- Portainer ce
- Watchtower
- nbr23/youtube-dl-server
- Nginx
- MariaDB
- PHP and MYPHPAdmin

I have followed a tutorial from Docker for local web development introduction why should you care ######1 for the LEMP setup a key note on which I did not undersatnd when I did the index.php file is to have $connection = new PDO('[DBMS]:host=[HOST];dbname=demo;charset=utf8', 'root', 'root'); - this is from great help from osteel the writer of the blog.

docker install on Debian ######2 and Install docker compose - <sup>3</sup> for the docker and docker compose install

sudo apt install -y libssl-dev python-dev libffi-dev libc6-dev gcc make python3-pip gnupg2 net-tools apt-transport-https ca-certificates curl gnupg-agent software-properties-common - these are what is recommended by Docker for alpine and install docker engine

Openmediavault 5 (OMV5) Complete Install and Setup including Portainer on PC ######4 for install and setup of Open Media vault not including the OMV extras because they do not include up to date docker install the one for the docker docs dose.


I have been using ######5 smart home beginners wesite to help with cleaning up my code and expanding on my containers for development.

For each .env file you will edit the file for each stack you create for organization of the conatiners<br />
```
COMPOSE_PROJECT_NAME={LEMP|OTHER|services} # this is to group the different area under each stack<br />
PUID=1000 # id command will show you this # for current user example uid=1000(user)
# Main linux user id that will be running server<br />
PGID=994 # id command will show you this # for current user example 994(docker)
# docker group id<br />
TZ={timezone} # the time zone for your area<br />
USERDIR={location to presistate date} # for me this is one the shares on open media vault
# this will be the location of the persistent data for all services running on the server - presistant data is the data 
# that will be saved for configuration files and services
```
<sup>1</sup> https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care
<sup>2</sup> https://docs.docker.com/engine/install/debian/
<sup>3</sup> https://docs.docker.com/compose/install/
<sup>4</sup> https://www.youtube.com/watch?v=A5ckT7pxrNY
<sup>5</sup> https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/
