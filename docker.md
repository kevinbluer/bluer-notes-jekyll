---
layout: page
title: Docker
permalink: /docker/
---

#### Core Commands

- docker ps -a / list all available containers
- docker ps / list all running containers
- docker start <id> / start a container
- docker images / list all images
- docker kill <id> / kill a particular running container
- docker rm <id> / remove a particular container

#### Docker Compose

"Compose is a tool for defining and running multi-container Docker applications."

#### Rocket Chat Example

docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --link mongo -d rocket.chat