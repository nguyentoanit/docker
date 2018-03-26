FROM centos:6.8
MAINTAINER nguyentoanit
#Update repository
RUN yum update --exclude=centos-release -y
RUN yum install -y epel-release http://rpms.famillecollet.com/enterprise/remi-release-6.rpm crontabs yum-utils httpd git postgresql postgresql-server

#Enable PHP reporistory and Install neccessary packages
RUN yum-config-manager --enable remi,remi-php56 && yum install -y php php-common php-pgsql php-pdo php-mbstring php-xml

#Set service to start on server boot
RUN chkconfig postgresql on && chkconfig httpd on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
