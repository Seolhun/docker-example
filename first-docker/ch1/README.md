## To build App using Docker - 1
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
```

### Docker and Dockerfile

#### 1)Dockerfile Setting
$ vim Dockerfile
```
FROM python:3.5
RUN pip install Flask==0.11.1 redis==2.10.5
RUN useradd -ms /bin/bash admin
USER admin
COPY app /app
WORKDIR /app
CMD ["python", "app.py"]
```
#### 2)Docker Build
$ docker build -t dockerapp:v0.1 .

#### 3)Docker images 확인
$ docker images

#### 4)Docker Images 실행
$ docker run -d -p 5000:5000 [image-id]

#### 5)Docker-machine 확인
$ docker-machine ls
* Url 복사 후 해당 run port와 삽입.
- ex) http://192.168.99.100:5000/

#### 6)실행된 Docker-Container 확인
docker ps

#### 7)해당 Container Bash 접근
docker exec -it [container-id] bash

#### 8)cpu check - 작동여부 확인
ps axu
