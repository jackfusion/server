LEMP Install through Docker I am setting up a LEMP install the way I would like it with

L - Open Media Vault - Linux
E - Nginx
M - MariaDB
P - PHP and MYPHPAdmin

I have followed a tutorial from Docker for local web development introduction why should you care - https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care for the LEMP setup a key note on which I did not undersatnd when I did the index.php file is to have $connection = new PDO('[DBMS]:host=[HOST];dbname=demo;charset=utf8', 'root', 'root'); - this is from great help from osteel the writer of the blog.

docker install on Debian - https://docs.docker.com/engine/install/debian/ and Install docker compose - https://docs.docker.com/compose/install/ for the docker and docker compose install

sudo apt install -y libssl-dev python-dev libffi-dev libc6-dev gcc make python3-pip gnupg2 net-tools apt-transport-https ca-certificates curl gnupg-agent software-properties-common - these are what is recommended by Docker for alpine and install docker engine

Openmediavault 5 (OMV5) Complete Install and Setup including Portainer on PC - https://www.youtube.com/watch?v=A5ckT7pxrNY for install and setup of Open Media vault not including the OMV extras because they do not include up to date docker install the one for the docker docs dose.

I have been using https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/ to help with cleaning up my code and expanding on my containers for development.

For each .env file you will edit the file for each stack you create for organization of the conatiners

COMPOSE_PROJECT_NAME={LEMP|OTHER|services} # this is to group the different area under each stack
PUID=1000 # id command will show you this # for current user example uid=1000(user)
- Main linux user id that will be running server
PGID=994 # id command will show you this # for current user example 994(docker)
- docker group id
TZ=America/Winnipeg # the time zone for your area
USERDIR={location to presistate date} # for me this is one the shares on open media vault
- this will be the location of the persistent data for all services running on the server - presistant data is the data that will be saved for configuration files
- and services
