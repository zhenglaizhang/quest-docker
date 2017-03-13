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
docker rm cont.
```

```bash
docker run -it --name=ubuntu -p 8080:8080 ubuntu bash


# 
docker stats --all --no-stream
docker stats ubuntu
docker stats $(docker ps -q) # TODO, use name instead of #
```
