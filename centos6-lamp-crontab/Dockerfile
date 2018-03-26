FROM centos:6.9
MAINTAINER nguyentoanit
#Update repository
RUN yum update -y

#Install crontab
RUN yum install -y http://rpms.famillecollet.com/enterprise/remi-release-6.rpm http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm crontabs yum-utils httpd mysql mysql-server

#Enable PHP reporistory and Install neccessary packages
RUN yum-config-manager --enable remi,remi-php56 && yum install -y php php-common php-mysql php-pdo

#Set service to start on server boot
RUN chkconfig mysqld on && chkconfig httpd on

#Expose ports
EXPOSE 80 443 3306

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash
