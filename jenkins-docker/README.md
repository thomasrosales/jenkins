# Jenkins & Docker

Contenedor docker con Docker y Jenkins dentro.

### Prerequisites

```
Windows 10
Docker
```

### Running

Bajar imagen de jenkis-docker, crear contenedor utilizando un volumen local y conectando a docker.sock y por ultimo cambiar los permisos para poder utilizarlo en jenkins. En ubuntu sería diferente el problema de permisos.

```
docker pull https://hub.docker.com/repository/docker/thomasdocker92/jenkins-test:46

docker run --name jenkins-docker -p 8080:8080 -p 50000:50000 -v C:\\<JENKINS_HOME_PATH>:/var/jenkins_home -v //var/run/docker.sock:/var/run/docker.sock -d jenkins-docker

docker exec -it <ID_CONTAINER_JENKINS-DOCKER> bash
root@... >> chmod 664 /var/run/docker.sock
root@... >> exit
```
