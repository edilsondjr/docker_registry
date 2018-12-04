# Docker Registry and Registry UI

Official Docker Registry is private image repository to store your custom container images.
To know more about: https://docs.docker.com/registry/

This is a docker-compose file that runs two containers:
- Docker Registry official image: https://hub.docker.com/r/library/registry/
- Docker Registry UI by konradkleine: https://hub.docker.com/r/konradkleine/docker-registry-frontend/


Docker version used to test and run: 18.09.0

For use with other docker versions, please change the version on first line of yml, according to official compatibility matrix:
https://docs.docker.com/compose/compose-file/#compose-and-docker-compatibility-matrix


Observations: 
- The registry service have been configured to function as a local proxy for the docker hub. To function only as a private registry, just comment the following line:
```sh
REGISTRY_PROXY_REMOTEURL=https://registry-1.docker.io
```
- The HTTPS registry service version needs valid certificate to run. Change the certificate path on registry_ssl.yml file in the following lines as you need:
```sh
- REGISTRY_HTTP_TLS_CERTIFICATE=/certs/docker.crt
- REGISTRY_HTTP_TLS_KEY=/certs/docker.key
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