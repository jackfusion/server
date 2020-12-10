<h1>Current Server Setup</h1>

<h2>Directoy layout</h2>

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


 <h1>Table Of Contents</h1>

<ul>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#introduction">Introduction</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#lemp">LEMP</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#debian-docker-and-open-media-vault">Debian Docker and Open Media Vault</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#enviroment-file">Enviroment File</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#sass">SASS</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#node-js">NODE JS</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#references">References</a></li>
</ul>

 <h1>Serivces</h1>

<ul>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#06-httpsgithubcomnginxincdocker-nginx">Nginx</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#08-httpsgithubcomdocker-librarymariadb">MariaDB</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#10-httpsgithubcomdocker-libraryphp">PHP</a> and <a href="https://github.com/jackfusion/server/blob/master/README.md#12-httpsgithubcomphpmyadmindocker">MYPHPAdmin</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#21-httpsgeshancomnpblog202011nodejs-with-docker">NODE JS</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#02-httpsgithubcomportainerportainer">Portainer ce</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#04-httpsgithubcomcontainrrrwatchtower">Watchtower</a></li>
    <li><a href="https://github.com/jackfusion/server/blob/master/README.md#14-httpsgithubcommanbearwizyoutube-dl-server">nbr23/youtube-dl-server</a></li>
</ul>

<h1>frameworks and extensions</h1>
- <a href="https://github.com/jackfusion/server/blob/master/README.md#20-httpsmybywayscomblogrunning-sass-in-a-container">SASS</a>

<h2>Introduction</h2>

<p>For docker run command to converted to docker-compose file I used <a href="https://www.composerize.com/">https://www.composerize.com/</a></p>

<p>This will be a current running setup of my server that will change as I develop things and add to the server.  Which means this repo will never be complete and will have only working setup for you to copy.  Meaning I will be constantly updating it when I add services.</p>

<p>I have split things up into 3 catagories currently.</p>

<p><b>Development</b> - This will be for any service that I will need for development meaning servers. Examples Nginx, PHP, MariaDB, PHPMyAdmin, Python, MEAN, NodeJS, Etc.<br />
<b>Services</b> - This will be this that are specific to Docker and the server for making it run or for backup services. Examples Portainter, Watchtower, Etc.<br />
<b>Other</b> - is for Other services that do not fall under the current list of services. Example Youtube-dl, etc.</p>

<p>The directory layout is for each service and the persistent data directory.</p>

<p>I will be keeping a runing list of links to the github repos, dockhubs, other sites and videos I use to setup my server for reference perposes so you can reference to them or if you would like more background on the service running here.</p>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>LEMP</h2>

<p>I have followed a tutorial from <a href="https://github.com/jackfusion/server/blob/master/README.md#15-httpstechosteelmepostsdocker-for-local-web-development-introduction-why-should-you-care">Docker for local web development introduction why should you care</a> for the LEMP setup a key note on which I did not undersatnd when I did the index.php file is to have $connection = new PDO('[DBMS]:host=[HOST];dbname=demo;charset=utf8', 'root', 'root'); - this is from great help from osteel the writer of the blog.</p>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>Debian, Docker and Open Media Vault</h2>
<p><a href="https://github.com/jackfusion/server/blob/master/README.md#16-httpsdocsdockercomengineinstalldebian">docker install on Debian</a> and <a href="https://github.com/jackfusion/server/blob/master/README.md#17-httpsdocsdockercomcomposeinstall">Install docker compose</a> for the docker and docker compose install</p>

<p>sudo apt install -y libssl-dev python-dev libffi-dev libc6-dev gcc make python3-pip gnupg2 net-tools apt-transport-https ca-certificates curl gnupg-agent software-properties-common - these are what is recommended by Docker for alpine and install docker engine
<a href="https://github.com/jackfusion/server/blob/master/README.md#18-httpswwwyoutubecomwatchva5ckt7pxrny">
Openmediavault 5 (OMV5) Complete Install and Setup including Portainer on PC</a> for install and setup of Open Media vault not including the OMV extras because they do not include up to date docker install the one for the docker docs dose.</p>

<p>I have been using <a href="https://github.com/jackfusion/server/blob/master/README.md#19-httpswwwsmarthomebeginnercomdocker-home-media-server-2018-basic">Home Media Sever</a> to help with cleaning up my code and expanding on my containers for development.</p>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>Enviroment File</h2>

For each .env file you will edit the file for each stack you create for organization of the conatiners<br />
<pre>
    <code>
COMPOSE_PROJECT_NAME={LEMP|OTHER|services} # this is to group the different area under each stack
PUID={id} # id command will show you this # for current user example uid=1000(user)
# Main linux user id that will be running server<br />
PGID={id} # id command will show you this # for current user example 994(docker)
# docker group id<br />
TZ={timezone} # the time zone for your area<br />
USERDIR={location to presistate date} # for me this is one the shares on open media vault
# this will be the location of the persistent data for all services running on the server - presistant data is the data 
# that will be saved for configuration files and services
    </code>
</pre>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>SASS</h2>

<p>To add SASS as a docker container I got the instructions from <a href="https://mybyways.com/blog/running-sass-in-a-container">running sass in a container</a></p>

<p>Here are the steps:</p>
<ol>
    <li>Download Sass latest version from Dart Sass GitHub.</li>
    <li>Create a Dockerfile (in the same folder as the .tar.gz please)
        <pre>
            <code>
        FROM debian
        ADD ./dart-sass-(change this to the version # i.e. 1.26.8)-linux-x64.tar.gz /opt/
        WORKDIR /opt/dart-sass
        ENTRYPOINT ["/opt/dart-sass/sass", "--watch", "/css"]
            </code>
        </pre>
        </li>
    <li>Then build it, tagging (-t) it with the name sass:
        <pre>
            <code>
        docker build -t sass ./
            </code>
        </pre>
        </li>
    <li>Run the image, mounting the --watch folder on the Host (/usr/[mylogin]/dev/css), which was specified in the Dockerfile above, in the Guest (/css): File         Sharing
        <pre>
            <code>
        docker run --rm -it -v /Users/[mylogin]/www/css:/css sass
            </code>
        </pre>
        or add the below to docker-compose file
        <pre>
            <code>
        sass:
            image: sass
            hostname: sass
            container_name: sass
            restart: always
            volumes:
               - ${USERDIR}/nginx/www/css:/css
            </code>
        </pre>
<p>use absolute paths - the usual, rename ${USERDIR}
make sure the folder is shared in Docker Desktop, under Preferences > Resources > File Sharing
it is possible to append any other arguments to the end of the command, e.g. docker run --rm -it -v /usr/me/dev/css:/src sass -s compressed for compressed output.<br>
Create or place any Sass stylesheets, e.g. mytheme.scss, and folders here - any file changes will trigger a compile auto-magically! Check out the examples of using Bulma with Sass CLI.</p></li>

<li>Now Sass watches your folder... forever. So, to terminate the running Sass container(s):
<pre>
    <code>
docker kill `docker ps -f ancestor=sass --format {{.ID}}`
    </code>
</pre>
the filter -f ancestor=sass finds the image created above, and
--format is used to return only the Container ID</li>
</ol>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>NODE JS</h2>

<p>To get node JS to work I so that I could ``` docker exec -it <container ID> /bin/bash ``` I followed this tutorial <a href="https://geshan.com.np/blog/2020/11/nodejs-with-docker/">nodejs with docker</a> but did the full version 15 as base not the alpine version because it will not work. So that you can bash into the container.</p>

<p>The other part I changed in the tutorial for my production system is not to install npm and node on the main system but to copy the server.js, package.json and package-lock.json from <a href="https://nodejs.org/en/docs/guides/nodejs-docker-webapp/">nodejs docker webapp</a>.  I will include them in the repo.</p>

<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>

<h2>References</h2>
<ol>
    <li><h6><a href="https://hub.docker.com/r/portainer/portainer-ce">https://hub.docker.com/r/portainer/portainer-ce</a></h6></li>
    <li><h6><a href="https://github.com/portainer/portainer">https://github.com/portainer/portainer</a></h6></li>
    <li><h6><a href="https://hub.docker.com/r/v2tec/watchtower">https://hub.docker.com/r/v2tec/watchtower</a></h6></li>
    <li><h6><a href="https://github.com/containrrr/watchtower">https://github.com/containrrr/watchtower</a></h6></li>
    <li><h6><a href="https://hub.docker.com/_/nginx">https://hub.docker.com/_/nginx</a></h6></li>
    <li><h6><a href="https://github.com/nginxinc/docker-nginx/">https://github.com/nginxinc/docker-nginx/</a></h6></li>
    <li><h6><a href="https://hub.docker.com/_/mariadb">https://hub.docker.com/_/mariadb</a></h6></li>
    <li><h6><a href="https://github.com/docker-library/mariadb">https://github.com/docker-library/mariadb</a></h6></li>
    <li><h6><a href="https://hub.docker.com/_/php">https://hub.docker.com/_/php</a></h6></li>
    <li><h6><a href="https://github.com/docker-library/php">https://github.com/docker-library/php</a></h6></li>
    <li><h6><a href="https://hub.docker.com/_/phpmyadmin">https://hub.docker.com/_/phpmyadmin</a></h6></li>
    <li><h6><a href="https://github.com/phpmyadmin/docker">https://github.com/phpmyadmin/docker</a></h6></li>
    <li><h6><a href="https://hub.docker.com/r/nbr23/youtube-dl-server">https://hub.docker.com/r/nbr23/youtube-dl-server</a></h6></li>
    <li><h6><a href="https://github.com/manbearwiz/youtube-dl-server">https://github.com/manbearwiz/youtube-dl-server</a></h6></li>
    <li><h6><a href="https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care">https://tech.osteel.me/posts/docker-for-local-web-development-introduction-why-should-you-care</a></h6></li>
    <li><h6><a href="https://docs.docker.com/engine/install/debian/<">https://docs.docker.com/engine/install/debian/</a></h6></li>
    <li><h6><a href="https://docs.docker.com/compose/install/">https://docs.docker.com/compose/install/</a></h6></li>
    <li><h6><a href="https://www.youtube.com/watch?v=A5ckT7pxrNY">https://www.youtube.com/watch?v=A5ckT7pxrNY</a></h6></li>
    <li><h6><a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/</a></h6></li>
    <li><h6><a href="https://mybyways.com/blog/running-sass-in-a-container">https://mybyways.com/blog/running-sass-in-a-container</a></h6></li>
    <li><h6><a href="https://geshan.com.np/blog/2020/11/nodejs-with-docker/">https://geshan.com.np/blog/2020/11/nodejs-with-docker/</a></h6></li>
    <li><h6><a href="https://nodejs.org/en/docs/guides/nodejs-docker-webapp/">https://nodejs.org/en/docs/guides/nodejs-docker-webapp/</a></h6></li>
</ol>
<p><a href="https://github.com/jackfusion/server/blob/master/README.md#table-of-contents">TOP</a><p>
