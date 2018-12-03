# Docker Registry and Registry UI

## SSL version of registry. Change the certificates path according to your environment.

Docker version used to test and run: 18.09.0

For use with other docker versions, please change the version on first line, according to compatibilty matrix on this link:
https://docs.docker.com/compose/compose-file/#compose-and-docker-compatibility-matrix

This is a docker-compose file that runs two containers
- docker registry official image: https://hub.docker.com/r/library/registry/
- docker registry UI by konradkleine: https://hub.docker.com/r/konradkleine/docker-registry-frontend/

Clone this repo and run:

Start:
```sh
docker-compose -f registry_ssl.yml up
```
Stop:
```sh
docker-compose -f registry_ssl.yml down
```