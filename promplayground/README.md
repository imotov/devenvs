Create .env file with the following content:
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

Note: if elasticsearch crashing it is most likely happening due to not enough memory given to docker
