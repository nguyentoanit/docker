FROM centos:6.8
MAINTAINER nguyentoanit
#Update repository
RUN yum update --exclude=centos-release -y
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-6.rpm epel-release centos-release-scl crontabs yum-utils httpd git

#Install PHP repository
RUN yum-config-manager --enable remi,remi-php56

#Install MariaDB repository
ADD config/MariaDB.repo /etc/yum.repos.d/MariaDB.repo

#Install neccessary packages
RUN yum install -y php php-common php-mysqlnd php-pdo php-mbstring php-xml MariaDB-server MariaDB-client

#Set service to start on server boot
RUN chkconfig mysql on
RUN chkconfig httpd on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash