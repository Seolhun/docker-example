## To build App using Docker - 5
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
```

### Docker Networking using Docker-Compose

#### 1. Docker-compose with network
```
$ docker-compose up -d
$ docker network ls
$ vi docker-compose.yml
```
```
version: '2'
services:
  dockerapp:
    build: .
    ports:
      - "5000:5000"
    # host directory : container directory
    volumes:
      - ./app:/app
    networks:
      - shooney_net

  redis:
    image: redis:3.2.0
  networks:
    - shooney_net

networks:
  shooney_net:
    driver: bridge
```
```
$ docker-compose up -d
$ docker network ls
```



