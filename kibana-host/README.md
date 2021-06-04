Runs the snapshot build of kibana against localhost elasticsearch

Create .env file with the following content:
```
ES_VERSION=7.12.1
ES_ADMIN_PASSWORD=changeme
```

To start an environment cd into the directory and run

```
$ docker-compose up
```
