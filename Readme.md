# Docker Compose HAProxy

## Introduction

Docker Compose for playing with HAProxy

## Contents

- [Run](#run)

## Run

### With NAT

```bash
# Start everything
docker-compose up -d

# Test everything
curl localhost:9000
curl localhost:9000
curl localhost:9000
curl localhost:9000

# Stop everything
docker-compose down -t 1
```

### With Defined IPs

```bash
# Start everything
docker-compose -f ips.docker-compose.yml up -d

# Test everything
docker run -it --rm --network haproxy-net appropriate/curl:3.1 curl 10.0.0.10:9000
docker run -it --rm --network haproxy-net appropriate/curl:3.1 curl 10.0.0.10:9000
docker run -it --rm --network haproxy-net appropriate/curl:3.1 curl 10.0.0.10:9000
docker run -it --rm --network haproxy-net appropriate/curl:3.1 curl 10.0.0.10:9000

# Stop everything
docker-compose -f ips.docker-compose.yml down -t 1
```
