## Nginx CAdvisor proxy Dockerfile

### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download image: `docker pull ohmydocker/nginx-cadvisor`

   (alternatively, you can build an image from Dockerfile: `docker build -t="ohmydocker/nginx-cadvisor" github.com/ohmydocker/nginx-cadvisor`)


### Usage

1. Prepare host with [cadvisor service cloud-config](https://github.com/lazarus1331/coreos-cloud-configs/blob/master/cadvisor.user-data).

2. Run docker container on host.

    docker run -d -p 3080:3080 ohmydocker/nginx-cadvisor

#### Attach persistent/shared directories

    docker run -d -p 80:80 -v <sites-enabled-dir>:/etc/nginx/conf.d -v <certs-dir>:/etc/nginx/certs -v <log-dir>:/var/log/nginx -v <html-dir>:/var/www/html dockerfile/nginx

After few seconds, open `http://<host>` to see the welcome page.


## Credits
This repository contains **Dockerfile** of [Nginx](http://nginx.org/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/dockerfile/nginx/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).
