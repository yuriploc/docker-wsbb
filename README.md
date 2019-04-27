# Access Banco do Brasil with Firefox in Docker

Warsaw in docker container. Warsaw is a security module, a.k.a Guardião, for brazilian internet banking. This project is compatible with Banco do Brasil and Caixa Econômica Federal.

## Pre-requisites

- Docker and Docker-Compose of your distro.

You must run Docker using a GNU/Linux distro running **Xorg**.

Be aware that some installations may run another display server, such as Wayland.

## Instructions

### TL;DR

```sh
docker run -ti --rm -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v $HOME/.Xauthority --net=host --pid=host --ipc=host docker.io/matsya/banco-do-brasil-firefox
```

Use `docker-compose` to build and run the docker container, rather than `docker run`, since environments and volumes are set on `docker-compose.yml`.

To build:
```sh
docker-compose build banco-do-brasil-firefox
```

To pulling existing image:
```sh
docker-compose pull
```

To first run:
```sh
docker-compose run --name banco-do-brasil-firefox banco-do-brasil-firefox
```

To other runs:
```sh
docker start -i -a banco-do-brasil-firefox
```

To purge everthing:
```sh
docker-compose down --rmi all
```

To force replace the container:
```sh
docker-compose up --force-recreate
```

The root password is **wsbb**.
