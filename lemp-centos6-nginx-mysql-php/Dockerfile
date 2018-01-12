FROM centos:6.9
MAINTAINER nguyentoanit
#Update repository
RUN yum update -y
RUN yum install -y epel-release crontabs mysql-server yum-utils http://rpms.remirepo.net/enterprise/remi-release-6.rpm

ADD configs/nginx.repo /etc/yum.repos.d/nginx.repo
#Install PHP repository
RUN yum-config-manager --enable remi-php72

#Install neccessary packages
RUN yum install -y php-fpm php php-common php-mysqlnd php-pdo php-mbstring php-xml nginx

#Set service to start on server boot
RUN chkconfig mysqld on
RUN chkconfig php-fpm on
RUN chkconfig nginx on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
