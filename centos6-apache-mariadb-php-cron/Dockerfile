FROM centos:6.8
MAINTAINER nguyentoanit
#Update repository
RUN yum update --exclude=centos-release -y
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-6.rpm epel-release centos-release-scl crontabs yum-utils httpd postgresql postgresql-server

#Install MariaDB repository
ADD config/MariaDB.repo /etc/yum.repos.d/MariaDB.repo

# Enable PHP repository and install neccessary packages
RUN yum-config-manager --enable remi,remi-php56 && yum install -y php php-common php-mysqlnd php-pdo php-mbstring php-xml php-pgsql php-gd php-mcrypt php-cli php-pear php-curl MariaDB-server MariaDB-client

#Set service to start on server boot
RUN chkconfig mysql on && chkconfig httpd on

EXPOSE 80 443 3306 5432

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
