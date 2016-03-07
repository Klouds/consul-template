# Consul-Template Configs and Templates

Config and Template file for consul-template for generating working configs for HAProxy and Caddy.

Pulls information populated by registrator into consul.



## Caddy(HTTPS by subdomain)

With registrator running, launch your containers with *ENV VARIABLE* SERVICE_TAGS=sub.domain.com like:

```
docker run --name ghost-blog -P -d -e SERVICE_TAGS=ghost.domain.com ghost
```

## HAProxy 

### HTTP

Same as running for caddy, launch your containers like:

```
docker run --name ghost-blog -P -d -e SERVICE_TAGS=ghost.domain.com ghost
```

### TCP

Due to the nature of TCP services, you can forward TCP services by HOSTIP:CONTAINER_PORT like so:

```
docker run --name minecraft -d -P -e SERVICE_TAGS=tcp -e EULA=TRUE itzg/minecraft-server
```

docker ps will look like:
```
e2a2ab48a7a9        itzg/minecraft-server           "/start"                 2 hours ago         Up 2 hours          0.0.0.0:32773->25565/tcp   minecraft
```

access at: HAPROXY_HOST_IP:32773
