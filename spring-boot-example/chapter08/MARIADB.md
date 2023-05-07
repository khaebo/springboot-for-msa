# 교재의 MySQL docker image 대신 MariaDB docker image 사용

## MariaDB Docker Image 설치
```
$ docker pull mariadb

$ docker images
```

## MariaDB Docker Container 실행
```
$ docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=msaDBr00t \
-v $HOME/DockerData/spring-tour-mariadb:/var/lib/mysql \
--name spring-tour-mariadb mariadb:latest \
--character-set-server=utf8mb4 \
--collation-server=utf8mb4_unicode_ci

$ docker ps
```

## MariaDB Docker Container 접속 후 데이터베이스 생성
```
$ docker exec -it spring-tour-mariadb /bin/bash
$ root@1657de337d74:/# mysql -u root -p

MariaDB> show databases;
MariaDB> CREATE DATABASE tour;
MariaDB [(none)]> use tour;
```

## MariaDB Docker Container 시작/정지 방법
```
$ docker start spring-tour-mariadb
$ docker stop spring-tour-mariadb 
```