# Docker compose files for test environments

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
VERSION=8.6.0
ELASTIC_PASSWORD=changeme
KIBANA_PASSWORD=changeme
ES_MAP_HOST=127.0.0.1:
KIBANA_MAP_HOST=127.0.0.1:
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

## promplayground

Starts the version of prometheus, node_exporter and grafana as well as kibana and elasticsearch.

The following environment variables are supported in .env file:

```
MAPHOST=127.0.0.1:
PROMETHEUS_VERSION=latest
NODE_EXPORTER_VERSION=latest
GRAFANA_VERSION=latest
GF_ADMIN_USER=admin
GF_ADMIN_PASSWORD=changeme
ES_VERSION=7.12.1
ES_ADMIN_PASSWORD=changeme
ES_MEMORY=512m
```

Before starting elasticsearch, generate certificates:

```
docker-compose -f create-certs.yml run --rm create_certs
```

To start an environment cd into the directory and run

```
$ docker-compose up -d
```

## kibana-host

Runs the snapshot build of kibana against localhost elasticsearch

Create .env file with the following content for released 7.x versions of
elasticsearch.

```
MAPHOST=127.0.0.1:
ES_VERSION=7.12.1
ES_ADMIN_PASSWORD=changeme
```

Create .env file with the following content if you want to run kibana against
an instant started with `./gradlew run`

```
MAPHOST=127.0.0.1:
ES_VERSION=8.0.0-SNAPSHOT
ES_ADMIN_USER=elastic-admin
ES_ADMIN_PASSWORD=elastic-password
```

To start an environment cd into the directory and run

```
$ docker-compose up
```

To re-pull a snapshot image use

```
$ docker-compose pull
```

## ubuntu

My ubuntu test environment

To setup create `home` directory and .env file

```
UBUNTU_VERSION=latest
```

To update everything:

```
docker-compose build --no-cache
```

To run:

```
docker-compose run --rm ubuntu
```

## clickhouse

The following environment variables are supported in .env file:

```
MAPHOST=127.0.0.1:
CLICKHOUSE_VERSION=latest
```

To run:

```
docker-compose up -d
```

Start the clickhouse client:

```
docker-compose exec clickhouse_server clickhouse-client
```

Or open http://localhost:8123 in your browser.
