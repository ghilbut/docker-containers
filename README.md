# Docker Containers

Local docker containers for personal development environment

## A. Network

```shell
$ docker network create ghilbut
$ docker network ls -f name=ghilbut
NETWORK ID     NAME      DRIVER    SCOPE
a5f0b9ee0332   ghilbut   bridge    local
```

>**Clean**
>```bash
>$ docker network rm ghilbut
>```

## B. MinIO

```shell
$ cd minio
$ docker-compose up -d
$ docker ps -f name=minio
CONTAINER ID   IMAGE                                              COMMAND                   CREATED         STATUS                   PORTS                                NAMES
9ecb21b59ffb   quay.io/minio/minio:RELEASE.2024-02-14T21-36-02Z   "/usr/bin/docker-ent…"   3 minutes ago   Up 3 minutes (healthy)   127.0.0.1:9000-9001->9000-9001/tcp   minio
```

**Console:** http://localhost:9001

>**Clean**
>```bash
>$ cd minio
>$ docker-compose down
>$ rm -f .data
>```

## C. PostgreSQL

```shell
$ cd postgres
$ docker-compose up -d
$ docker ps -f name=postgres
CONTAINER ID   IMAGE           COMMAND                   CREATED         STATUS                   PORTS                      NAMES
3feae1b6f176   postgres:16.2   "docker-entrypoint.s…"   3 minutes ago   Up 3 minutes (healthy)   127.0.0.1:5432->5432/tcp   postgres
```

>**Clean**
>```bash
>$ cd postgres
>$ docker-compose down
>$ rm -f .data
>```
