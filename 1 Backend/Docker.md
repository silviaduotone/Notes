# Docker



## Starting docker 

1. start docker plugin
2. cd docker main folder
3. sh start.sh
4. Cdp [namefolder]
5. npm run dev
6. exit or ctrl+c
7. Docker-compose down



## Adding a new project

1. after starting docker run wizzard
2. sudo nano/etc/hosts
3. add entry projectName.site 127.0.0.1
4. add .htaccess
5. in doc config add also the new hosting
6. add the missing less gulp folders in the atomic theme
7. restart docker container
8. load database
   1. if database is from an online website, search replace https to http and site.ch to site.site
9. load plugin and uploads
10. git clone from bitbucket
11. run npm install



## Starting new feature





# Without Atomic Docker

in html folder in docker (when you start the shell)
mkdir directoryprogetto
cd directoryprogetto
wp core download
wp core config --dbname=portfolio --dbhost=mysql --dbuser=root --dbpass=docker
wp db create

(if the database is new, not if you import!)
wp core install --url=portfolio.site --title=Portfolio --admin_user=silvia --admin_email=email@email.com



## Weird notes on my notebook (docker window?)

1. Cd docker dev folder
2. Docker-compose up -d (-d stands for detached mode, no mysql root?)
3. wp core download
4. v hosts in window
   1. Note pad, run as administrator
   2. Open window/system32/driver/etc/hosts/*all files
5. docker compose restart
6. create ssh-keygen
7. Docker-compose build
8. search replace https to http
9. Uploads plugins db





# sudo nano

sudo nano /etc/hosts
add the new site!

# VHOSTS

cd dev-docker/config/vhosts/default.conf

open default config and modify it by adding the new site.

## restart the container apache
only necessary when you change something, when you change the vhost!


# create o import child theme

nella directory, in wp content, themes!
### add directory of the child theme
git clone git@github.com:thomome/anyfid.git
### import database

wp db import name.sql

copy paste the upload and plugins

## add htacces file to allow wordpress to reroute stuff
to the main folder


## cpd folder

npm install
npm run dev to show how quick it is



## error maximum function nest

\- xdebug.max_nesting_level = -1
\- docker folder
\- config
\- php.ini modify