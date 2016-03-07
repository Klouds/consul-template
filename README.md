##Consul-Template

Template files and consul-template configs for various load-balancers/proxies

Routes by subdomain when launching docker containers registered in consul with SERVICE_TAGS=sub.domain.com

example:

```
docker run --name ghost -d -P -e SERVICE_TAGS=ghost.klouds.org ghost

```

Currently has files for:

-Caddy (github.com/mholt/caddy)
-HAProxy (TCP by IP:PORT, http by subdomain)
