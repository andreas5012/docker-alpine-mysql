Docker + Alpine-3.7 + Mysql/MariaDB-10.1.37

#### parameter

* `MYSQL_ROOT_PWD` : root Password   default "mysql"
* `MYSQL_USER`     : new User
* `MYSQL_USER_PWD` : new User Password
* `MYSQL_USER_DB`  : new Database for new User

#### build image

```
$ docker build -t orozcohsu/docker-alpine-mysql .
```

#### run a default contaier

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 orozcohsu/docker-alpine-mysql
```

#### run a container with new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=iii -e MYSQL_USER_PWD=iii orozcohsu/docker-alpine-mysql
```

#### run a container with new Database for new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=123 -e MYSQL_USER=iii -e MYSQL_USER_PWD=iii -e MYSQL_USER_DB=chatbot orozcohsu/docker-alpine-mysql
```

#### run docker-compose up -d in docker-compose.yml folder

```
$ docker-compose up -d
```
