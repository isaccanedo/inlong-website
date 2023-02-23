---
title: Docker
sidebar_position: 2
---

Deploy all InLong module by Docker Compose, it's only available for development.

Requirements:

- [Docker](https://docs.docker.com/engine/install/) 19.03.1+
- Docker Compose 1.29.2+

## Deploy

Manually copy SQL files from `inlong-manager/manager-web/sql` to the `docker/compose/sql` directory.

```shell
cp inlong-manager/manager-web/sql/apache_inlong_manager.sql  docker/docker-compose/sql
```

Then, start all components.

```shell
docker-compose up -d
```

## Use InLong

After all containers run successfully, you can access `http://localhost` with default account:

```shell
User: admin
Password: inlong
```

## Destroy

```shell
docker-compose down
```
