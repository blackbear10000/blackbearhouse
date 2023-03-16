# 基本信息

- 官网：https://www.postgresql.org/
- 官方文档：https://www.postgresql.org/docs/15/preface.html
- 菜鸟教程：https://www.runoob.com/postgresql/postgresql-tutorial.html
- Docker 安装与部署教程：https://zhuanlan.zhihu.com/p/434248483
- 在Docker中运行PostgreSQL + pgAdmin 4：https://cloud.tencent.com/developer/article/1679495

# 安装

```
docker pull postgres:15.2
docker images

docker volume create pgdata
docker volume inspect pgdata

docker run --name postgres15 -e POSTGRES_PASSWORD=pg123456 -p 5432:5432 -v pgdata:/var/lib/postgresql/data -d postgres:15.2

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


# 安装 pgadmin4

```
docker pull dpage/pgadmin4
docker run -d -p 5433:80 --name pgadmin4 -e PGADMIN_DEFAULT_EMAIL=test@123.com -e PGADMIN_DEFAULT_PASSWORD=123456 dpage/pgadmin4
```

打开浏览器访问 http://localhost:5433/