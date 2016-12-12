---
layout: page
title: Docker
permalink: /docker/
---

"Docker is the world's leading software containerization platform"

#### Core Commands

- docker ps -a / list all available containers on any given system
- docker ps / list all running containers
- docker start <id> / start a container
- docker images / list all images
- docker kill <id> / kill a particular running container
- docker rm <id> / remove a particular container
- docker rmi <id> / remove a particular image
- docker logs <name> / show the logs for a given container

#### Examples Commands

- `docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --link mongo -d rocket.chat`
- `docker run -d --hostname my-rabbit --name some-rabbit -p 8080:15672 -p 5672:5672 rabbitmq:3-management`

#### Currently In Use

- [Ghost](https://hub.docker.com/_/ghost/)
- [RabbitMQ](https://hub.docker.com/r/library/rabbitmq/)
- [Logstash](https://hub.docker.com/_/logstash/)

### General Notes

- Docker can build images automatically by reading the instructions from a [Dockerfile](https://docs.docker.com/engine/reference/builder/)
- Note that to expose multiple ports you can simply use mutiple `-p` tags

#### Docker Compose

"Compose is a tool for defining and running multi-container Docker applications."

#### Docker Swarm

"Docker Swarm is the native orchestration engine used by Docker Datacenter to operate and manage Docker apps at scale"