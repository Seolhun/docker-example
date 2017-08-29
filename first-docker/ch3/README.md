## To build App using Docker - 2 with Redis
[My Github repository](https://github.com/Seolhun/docker-test/tree/master/first-docker/ch3)
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
```

### Deep Dive Docker-Compose

#### 1. Docker Compose Function
```
$ docker-compose up -d
$ docker-compose ps

$ docker-compose logs
$ docker-compose logs dockerapp

$ docker-compose stop
$ docker-compose rm
$ docker-compose ps

```

#### 2. Images Re-build using docker-compose
- admin > your name

```
$ vim Dockerfile

FROM python:3.5
RUN pip install Flask==0.11.1 redis==2.10.5
RUN useradd -ms /bin/bash admin
USER admin
WORKDIR /app
CMD ["python", "app.py"]
```

```
$ docker exec -it 9b317316832e bash
```
- But, Not change bash name, because Docker Compose not re-build Images

```
$ docker-compose build
$ docker-compose up -d
$ docker exec -it 9b317316832e bash
```
- Re-creating Images into Container, you can see that changed bash name