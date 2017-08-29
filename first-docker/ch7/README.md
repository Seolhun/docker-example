# To build App using Docker - 7

[My Github repository](https://github.com/Seolhun/docker-test/tree/master/first-docker/ch7)
```
OS : macOS Sierra 10.12.5
Docker version : Docker version 17.06.0-ce, build 02c1d87
Docker-machine version : version 0.12.2, build 9371605
```

## 1)Registering Digitalocean API access token
- [Register DigitalOcean Token](https://cloud.digitalocean.com/settings/api/tokens?i=3a032f)

## 2)Install Docker-machine
- [Docker-machin Install](https://docs.docker.com/machine/install-machine/)

---

## Docker Machine and Create DockerMachine Using DigitalOcean
```bash
docker-machine ls
docker-machine create --driver digitalocean --digitalocean-access-token ${DigitalOcean_TokenValue} dockershooney
docker-machine env dockershooney
eval $(docker-machine env dockershooney)
```

Created prod.yml
```yaml
version: '2'
services:
  dockerapp:
    image: jleetutorial/dockerapp
    ports:
      - "5000:5000"

  redis:
    image: redis:3.2.0
```

```bash
docker-compose -f prod.yml up -d
docker-machine ls
docker info
```
Checking OS(ubuntu 16.04) and Provisor(DigitalOcean)
- YourDigitalOceanIP:5000



