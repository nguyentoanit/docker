FROM centos:6.8
MAINTAINER nguyentoanit
#Update repository
RUN yum update --exclude=centos-release -y
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-6.rpm https://download.postgresql.org/pub/repos/yum/9.6/redhat/rhel-6-x86_64/pgdg-centos96-9.6-3.noarch.rpm epel-release crontabs yum-utils httpd git

RUN yum-config-manager --enable remi,remi-php56

#Install neccessary packages
RUN yum install -y php php-common php-pgsql php-pdo php-mbstring php-xml postgresql96-server postgresql96

#Set service to start on server boot
RUN chkconfig postgresql-9.6 on
RUN chkconfig httpd on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash