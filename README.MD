# Docker Registry and Registry UI

Docker version used to test and run: 18.09.0

For use with other docker versions, please change the version on first line, according to this official compatibility matrix:
https://docs.docker.com/compose/compose-file/#compose-and-docker-compatibility-matrix

This is a docker-compose file that runs two containers:
- docker registry official image: https://hub.docker.com/r/library/registry/
- docker registry UI by konradkleine: https://hub.docker.com/r/konradkleine/docker-registry-frontend/

- The registry service have been configured to function as a local proxy for the docker hub. To function only as a private registry, just comment the following line in:
```sh
REGISTRY_PROXY_REMOTEURL=https://registry-1.docker.io
```

To run, clone this repo and run:

## HTTP

Start:
```sh
docker-compose -f registry.yml up -d
```
Stop:
```sh
docker-compose -f registry.yml down
```

## HTTPS

Start:
```sh
docker-compose -f registry_ssl.yml up -d
```
Stop:
```sh
docker-compose -f registry_ssl.yml down
```