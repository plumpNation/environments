# DOCKER-VERSION 0.3.4

MAINTAINER Gavin King <plumpnation@gmail.com>

FROM ubuntu:precise

RUN apt-get update

RUN apt-get -y upgrade

RUN DEBIAN_FRONTEND=noninteractive apt-get -y install mysql-client mysql-server apache2 libapache2-mod-php5 pwgen python-setuptools vim-tiny php5-mysql

EXPOSE 80
