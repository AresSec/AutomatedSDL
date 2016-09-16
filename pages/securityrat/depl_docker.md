---
title: Docker Deployment
#keywords: sample
summary: "Docker deployment is suitable if you want to setup the tool quickly and play around with it. It is not suitable for production deployment."
sidebar: home_sidebar
permalink: depl_docker.html
#simple_map: true
#map_name: usermap
#box_number: 1
folder: product2
---


## Quick start
Download the docker image:

```
docker pull securityrat/all_in_one
```

In order to start the image and load SecurityRAT in the browser, follow the instructions at the [SecurityRAT Page on DockerHub](https://hub.docker.com/r/securityrat/all_in_one/)

## Contents of the Docker Image

The docker image contains the following parts:

* SecurityRAT tool
* Apereo CAS for authentication
* MySQL Database containing the default requirement set

{% include links.html %}
