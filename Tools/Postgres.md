# 基本信息

- 官网：https://www.postgresql.org/
- 官方文档：https://www.postgresql.org/docs/15/preface.html
- 菜鸟教程：https://www.runoob.com/postgresql/postgresql-tutorial.html
- Docker 安装与部署教程：https://zhuanlan.zhihu.com/p/434248483

# 安装

```
docker pull postgres:15.2
docker images

docker volume create pgdata
docker volume inspect pgdata

docker run --name postgres15 -e POSTGRES_PASSWORD=password -p 5040:5040 -v pgdata:/var/lib/postgresql/data -d postgres:15.2

sudo ls /var/lib/docker/volumes/pgdata/_data
```

# 进入容器创建角色

```
docker ps
docker exec -it postgres15 /bin/bash

su postgres
createuser -P -s -e shuai

psql
create database chainlink owner=shuai
\l
```