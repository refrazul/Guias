# Docker Postgres

## Instalación
Secuencia para ponerlo en funcionamiento en un contenedor. Creamos “postsql1” basándonos en la imágen “postgres” recién bajada.

```bash
$ docker pull postgres
$ docker run -p 5432:5432 --name postsql1 -e POSTGRES_PASSWORD=yourPassword -d postgres
```

La imágen de PostgreSQL mide solo 348 Mb, y necesita 12 megas para funcionar.

```bash
$ docker images
```
```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
postgres            latest              f88dfa384cc4        3 weeks ago         348MB
```

Podemos crear otro contenedor para correr el cliente, lo llamamos “psql”, lo linkeamos al servidor y usamos el modificador “–rm” para que, cuando el contenedor se apague se borre automáticamente.
```bash
$ docker run -it --rm --name psql --link postsql1:postgres postgres psql -h postgres -U postgres
```
```
Password for user postgres:
psql (10.0)
Type "help" for help.

postgres=# select 1;
----------
        1
(1 row)


postgres=# \q
```

## Instalar cliente de postgres

```bash
$ sudo apt-get install postgresql-client
```

## Conectar cliente con Postgres docker

```bash
$ psql -h 127.0.0.1 -U postgres
```

## Comandos docker utiles
- docker stop 2dd32f7e9792  	==> Detiene el contenedor
- docker start 2dd32f7e9792		==> Lanza el contenedor
- docker ps -a					==> Lista procesos de los contenedores