---
layout: page
title: Docker
permalink: /docker/
---

#### Core Commands

- docker ps
- docker images
- docker kill
- docker rm

#### Rocket Chat Example

docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --link mongo -d rocket.chat