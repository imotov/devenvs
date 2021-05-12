# Docker compose files for test environments

## Instructions

To start an environment cd into the directory and run

```
$ docker-compose up -d
```


When done, stop Elasticsearch and Kibana by running:

```
$ docker-compose down
```

To update the rebuild the image after update run:

```
$ docker-compose build
```

## elasticstack

Starts the latest version of Elasticsearch and Kibana but you can specify version
in `.env` file. For example:
```
VERSION=7.12.1
```

After startup you can connect to Elasticsearch at http://localhost:9200/ and
Kibana at http://localhost:5601/


## prometheus

Starts the latest version of prometheus, node_exporter and grafana but you can specify version
in `.env` file. For example:
```
PROMETHEUS_VERSION=v2.26.0
NODE_EXPORTER_VERSION=v1.1.2
GRAFANA_VERSION=7.5.6
```

After startup you can connect to prometheus at http://localhost:9090/ and
grafana at http://localhost:3000/
