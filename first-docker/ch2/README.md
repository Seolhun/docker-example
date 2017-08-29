## To build App using Docker - 2 with Redis
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
```

### Docker-Compose

#### 1)Docker pull Redis & run Redis
$ docker run -d --name redis redis:3.2.0

#### 2)Docker Container Check
$ docker ps

#### 3)Docker Build Comtainer
$ docker build -t dockerapp:v0.3

#### 4)Docker Run built container
$ docker run -d -p 5000:5000 --link redis dockerapp:v0.3

#### 5)Redis Container Link 확인하기.
$ docker exec -it b7bc8676a983 bash
$ more /etc/hosts 
$ ping redis

#### 6)Docker Compose
$ touch docker-compose.yml
$ docker-compose up


