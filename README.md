# dinghy-lamp-stack
Full LAMP stack development environment using docker and dinghy.

Took a while to get this up and running on MacOS. Figured I would save others some time.

## Installation

Head over to https://www.docker.com and download and install docker.

We will require dinghy to make our lives easier. https://github.com/codekitchen/dinghy

Dinghy has some cool addons compared to docker machine.

Once Dinghy has been installed, you can shutdown the docker agent running.

## Docker images

I try and make use of webdevops images where I can. https://github.com/webdevops/Dockerfile

## MacOSX tweaks

Really struggled to get xdebug up and running. Eventually tracked it down to the 
docker image not being able to access the host. 

This helped solve that https://gist.github.com/ralphschindler/535dc5916ccbd06f53c1b0ee5a868c93.

## Docker compose

Run docker-compose up to start cluster

You should be able to access the test site at http://app.webserver.docker.

## Applications

The current applications are stored in docker/applications.

### Bower

If you use bower for resource management. 

To run a bower update, execute:

docker-compose run bower update

### Composer

If you use composer for resource management. 

To run a composer update, execute:

docker-compose run composer update

### Httpd

Apache server. 

### Mailhog

If your are sending email from your application. Mailhog is a cool tool to test emails. https://github.com/mailhog/MailHog

Web UI at http://app.mail.docker/. 

### MySQL 

Data file is read from data/sql/data.sql. You can obviously change this.

### PHP-FPM

Executes PHP scripts.

### PHPMyAdmin



### Redis

Caching layer. You can obviously swop this out with memcacheif you prefer.

You can pass through commands using docker exec.

Clear all cache:
docker-compose exec redis redis-cli flushall

