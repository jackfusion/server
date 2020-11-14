# Current Server Setup

## Directoy layout

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
│   │   │       └── css <br />
│   │   │       └── sass <br />
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
- <a href="https://github.com/jackfusion/server/blob/master/README.md#02-httpsgithubcomportainerportainer">Portainer ce</a>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#04-httpsgithubcomcontainrrrwatchtower">Watchtower</a>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#06-httpsgithubcomnginxincdocker-nginx">Nginx</a>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#08-httpsgithubcomdocker-librarymariadb">MariaDB</a>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#10-httpsgithubcomdocker-libraryphp">PHP</a> and <a href="https://github.com/jackfusion/server/blob/master/README.md#12-httpsgithubcomphpmyadmindocker">MYPHPAdmin</a>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#14-httpsgithubcommanbearwizyoutube-dl-server">nbr23/youtube-dl-server</a>

#frameworks and extensions
- SASS

This will be a current running setup of my server that will change as I develop things and add to the server.  Which means this repo will never be complete and will have only working setup for you to copy.  Meaning I will be constantly updating it when I add services.  

I have split things up into 3 catagories currently.

<b>Development</b> - This will be for any service that I will need for development meaning servers. Examples Nginx, PHP, MariaDB, PHPMyAdmin, Python, MEAN, NodeJS, Etc.<br />
<b>Services</b> - This will be this that are specific to Docker and the server for making it run or for backup services. Examples Portainter, Watchtower, Etc.<br />
<b>Other</b> - is for Other services that do not fall under the current list of services. Example Youtube-dl, etc.<br />

The directory layout is for each service and the persistent data directory.

I will be keeping a runing list of links to the github repos, dockhubs, other sites and videos I use to setup my server for reference perposes so you can reference to them or if you would like more background on the service running here.

I have followed a tutorial from <a href="https://github.com/jackfusion/server/blob/master/README.md#15-httpstechosteelmepostsdocker-for-local-web-development-introduction-why-should-you-care">Docker for local web development introduction why should you care</a> for the LEMP setup a key note on which I did not undersatnd when I did the index.php file is to have $connection = new PDO('[DBMS]:host=[HOST];dbname=demo;charset=utf8', 'root', 'root'); - this is from great help from osteel the writer of the blog.

<a href="https://github.com/jackfusion/server/blob/master/README.md#16-httpsdocsdockercomengineinstalldebian">docker install on Debian</a> and <a href="https://github.com/jackfusion/server/blob/master/README.md#17-httpsdocsdockercomcomposeinstall">Install docker compose</a> for the docker and docker compose install

sudo apt install -y libssl-dev python-dev libffi-dev libc6-dev gcc make python3-pip gnupg2 net-tools apt-transport-https ca-certificates curl gnupg-agent software-properties-common - these are what is recommended by Docker for alpine and install docker engine
<a href="https://github.com/jackfusion/server/blob/master/README.md#18-httpswwwyoutubecomwatchva5ckt7pxrny">
Openmediavault 5 (OMV5) Complete Install and Setup including Portainer on PC</a> for install and setup of Open Media vault not including the OMV extras because they do not include up to date docker install the one for the docker docs dose.


I have been using <a href="https://github.com/jackfusion/server/blob/master/README.md#19-httpswwwsmarthomebeginnercomdocker-home-media-server-2018-basic">Home Media Sever</a> to help with cleaning up my code and expanding on my containers for development.

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
## SASS

To add SASS as a docker container I got the instructions from <a href="https://mybyways.com/blog/running-sass-in-a-container">running sass in a container</a>

Here are the steps:

Download Sass latest version from Dart Sass GitHub.

Create a Dockerfile (in the same folder as the .tar.gz please):
```
FROM google/dart
ADD ./dart-sass-(change this to the version # i.e. 1.26.8)-linux-x64.tar.gz /opt/
WORKDIR /opt/dart-sass
ENTRYPOINT ["/opt/dart-sass/sass", "--watch", "/css"]
```
Then build it, tagging (-t) it with the name sass:
```
docker build -t sass ./
```
Run the image, mounting the --watch folder on the Host (/usr/[mylogin]/dev/css), which was specified in the Dockerfile above, in the Guest (/css): File Sharing
```
docker run --rm -it -v /Users/[mylogin]/www/css:/css sass
```
use absolute paths - the usual, rename [mylogin]
make sure the folder is shared in Docker Desktop, under Preferences > Resources > File Sharing
it is possible to append any other arguments to the end of the command, e.g. docker run --rm -it -v /usr/me/dev/css:/src sass -s compressed for compressed output.
Create or place any Sass stylesheets, e.g. mytheme.scss, and folders here - any file changes will trigger a compile auto-magically! Check out the examples of using Bulma with Sass CLI.

Now Sass watches your folder... forever. So, to terminate the running Sass container(s):
```
docker kill `docker ps -f ancestor=sass --format {{.ID}}`
```
the filter -f ancestor=sass finds the image created above, and
--format is used to return only the Container ID


###### 01 https://hub.docker.com/r/portainer/portainer-ce
###### 02 https://github.com/portainer/portainer
###### 03 https://hub.docker.com/r/v2tec/watchtower
###### 04 https://github.com/containrrr/watchtower
###### 05 https://hub.docker.com/_/nginx
###### 06 https://github.com/nginxinc/docker-nginx/
###### 07 https://hub.docker.com/_/mariadb
###### 08 https://github.com/docker-library/mariadb
###### 09 https://hub.docker.com/_/php
###### 10 https://github.com/docker-library/php
###### 11 https://hub.docker.com/_/phpmyadmin
###### 12 https://github.com/phpmyadmin/docker
###### 13 https://hub.docker.com/r/nbr23/youtube-dl-server
###### 14 https://github.com/manbearwiz/youtube-dl-server
###### 15 https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care
###### 16 https://docs.docker.com/engine/install/debian/
###### 17 https://docs.docker.com/compose/install/
###### 18 https://www.youtube.com/watch?v=A5ckT7pxrNY
###### 19 https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/
