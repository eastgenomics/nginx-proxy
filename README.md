# nginx-reverse-proxy
docker compose file for nginx-reverse-proxy in dev or prod server.
The script requires external network to be created before spinning up the nginx proxy

# Usage
1. create network `docker network create <network name>`
2. spin up nginx proxy `docker compose up -d`

Any other docker containers that spun up will need to be in the same network
```
networks:
  default:
    name: <network name>
    external: true
```
and have environments `VIRTUAL_HOST` and `VIRTUAL_PATH`

`VIRTUAL_HOST` is the hostname e.g. dev-genomics.net....\
`VIRTUAL_PATH` is the subdirectory e.g. /genetics_ark

# Reference
https://github.com/nginx-proxy/nginx-proxy
