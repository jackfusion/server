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
