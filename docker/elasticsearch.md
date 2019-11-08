# Docker Elasticsearch

## Instalación
Secuencia para ponerlo en funcionamiento en un contenedor. 

Descargamos la imagen de Elasticsearch
```bash
$ docker pull docker.elastic.co/elasticsearch/elasticsearch:7.1.1
```

```
docker images
REPOSITORY                                      TAG                 IMAGE ID            CREATED             SIZE
postgres                                        latest              f88dfa384cc4        3 weeks ago         348MB
docker.elastic.co/elasticsearch/elasticsearch   7.1.1               b0e9f9f047e6        5 months ago        894MB
```

Corremos la imagen que acabamos de descargar

```bash
$ docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.1.1
```

## Validar Elasticsearch

Accedemos a la url http://localhost:9200/ y tenemos que ver algo como esto

<img href="elastic_validar.png"/>



