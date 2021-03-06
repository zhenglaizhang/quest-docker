# quest-docker
All stuff about Docker As A Service &amp; Micro-service on docker


## Setup

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.11.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

```

## docker-compose
```bash
docker-compose up -d
docker-compose ps
docker-compose stop
docker-compose rm
docker-compose kill
docker-compose scale web=5
docker rm container_name
```


## Simple Monitoring
```bash
docker run -it --name=ubuntu -p 8080:8080 ubuntu bash

# 
docker stats --all --no-stream
docker stats ubuntu
docker stats $(docker ps -q) # TODO, use name instead of #
docker top cont1
docker top cont1 -aux
docker top cont1 -faux # any options to `ps`


docker exec -it cont. bash
bash# ps aux
bash# top
```


## Container Advisor
`Let Me Contain That For You` or `lmctfy`

```bash
docker run \
  --detach=true \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --publish=8080:8080 \
  --privileged=true \
  --name=cadvisor \
  google/cadvisor:latest
  
sudo docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --publish=8080:8080 \
  --detach=true \
  --name=cadvisor \
  google/cadvisor:latest
```
