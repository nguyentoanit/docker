FROM centos:6.9
MAINTAINER nguyentoanit
#Update repository
RUN yum update -y && yum install -y epel-release crontabs mysql-server yum-utils http://rpms.remirepo.net/enterprise/remi-release-6.rpm

ADD configs/nginx.repo /etc/yum.repos.d/nginx.repo

#Enable PHP repository and Install neccessary packages
RUN yum-config-manager --enable remi-php72 && yum install -y php-fpm php php-common php-mysqlnd php-pdo php-mbstring php-xml nginx

#Set service to start on server boot
RUN chkconfig mysqld on && chkconfig php-fpm on && chkconfig nginx on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
