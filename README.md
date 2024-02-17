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
9ecb21b59ffb   quay.io/minio/minio:RELEASE.2024-02-14T21-36-02Z   "/usr/bin/docker-ent…"   2 minutes ago   Up 2 minutes (healthy)   127.0.0.1:9000-9001->9000-9001/tcp   minio
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
3feae1b6f176   postgres:16.2   "docker-entrypoint.s…"   2 minutes ago   Up 2 minutes (healthy)   127.0.0.1:5432->5432/tcp   postgres
```

>**Clean**
>```bash
>$ cd postgres
>$ docker-compose down
>$ rm -f .data
>```

## D. Grafana Stack

**REF:** https://github.com/grafana/intro-to-mltp

### D1. Mimir

```shell
$ cd grafana-mimir
$ docker-compose up -d
$ docker ps -f name=mimir
CONTAINER ID   IMAGE                  COMMAND                   CREATED         STATUS                   PORTS                                NAMES
aa5f6a3df816   grafana/mimir:2.11.0   "/bin/mimir -ingeste…"   2 minutes ago   Up 2 minutes (healthy)   8080/tcp, 127.0.0.1:9009->9009/tcp   mimir
```

>**Clean**
>```bash
>$ cd grafana-mimir
>$ docker-compose down
>$ rm -f .data
>```

### D2. Loki

```shell
$ cd grafana-loki
$ docker-compose up -d
$ docker ps -f name=loki
CONTAINER ID   IMAGE                COMMAND                   CREATED         STATUS                   PORTS                                                                          NAMES
3d139038dadf   grafana/loki:2.9.4   "/usr/bin/loki -conf…"   2 minutes ago   Up 2 minutes (healthy)   127.0.0.1:3100->3100/tcp, 127.0.0.1:7946->7946/tcp, 127.0.0.1:9095->9095/tcp   loki
```

>**Clean**
>```bash
>$ cd grafana-loki
>$ docker-compose down
>$ rm -f .data
>```

### D3. Tempo

```shell
$ cd grafana-tempo
$ docker-compose up -d
$ docker ps -f name=tempo
CONTAINER ID   IMAGE                 COMMAND                   CREATED         STATUS                   PORTS                                                                                                                                                        NAMES
bcea0da0431a   grafana/tempo:2.3.1   "/tempo -config.file…"   2 minutes ago   Up 2 minutes (healthy)   127.0.0.1:3200->3200/tcp, 127.0.0.1:4317-4318->4317-4318/tcp, 127.0.0.1:9411->9411/tcp, 127.0.0.1:14250->14250/tcp, 127.0.0.1:55680-55681->55680-55681/tcp   tempo
```

>**Clean**
>```bash
>$ cd grafana-tempo
>$ docker-compose down
>$ rm -f .data
>```

### D4. Pyroscope

```shell
$ cd grafana-pyroscope
$ docker-compose up -d
$ docker ps -f name=pyroscope
CONTAINER ID   IMAGE                     COMMAND                  CREATED       STATUS                 PORTS                      NAMES
73dc75f828d0   grafana/pyroscope:1.4.0   "/usr/bin/pyroscope …"   2 minutes ago   Up 2 minutes (healthy)   127.0.0.1:4040->4040/tcp   pyroscope
```

>**Clean**
>```bash
>$ cd grafana-pyroscope
>$ docker-compose down
>$ rm -f .data
>```
