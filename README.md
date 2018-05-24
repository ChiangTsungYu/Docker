# Docker


Ubuntu16.04 适用docker安装MySQL,并将数据挂载到本地目录

1、查找mysql镜像
sudo docker search mysql

2、拉取mysql镜像
sudo docker pull mysql

3、运行mysql镜像，名字为mysql， 将/var/lib/mysql挂载到本地目录/opt/mysql/data ，设置root密码为123456

sudo docker run -p 3306:3306 --name mysql   -v /opt/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:latest

4、查看容器启动情况,-a包括未启动的容器
sudo docker ps

5、进入容器
sudo docker exec -it mysql /bin/bash

mysql -u root -p 123456 登陆容器内数据库


停止容器
sudo docker stop mysql

删除容器（非运行状态）
sudo docker rm mysql
