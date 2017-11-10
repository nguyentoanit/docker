FROM centos:6.9
MAINTAINER nguyentoanit
#Update repository
RUN yum update -y

#Install crontab
RUN yum install -y crontabs yum-utils httpd mysql mysql-server wget

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

#Installl Apache, PHP5.6 and Mysql
RUN wget http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
RUN wget http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN rpm -Uvh remi-release-6*.rpm epel-release-6*.rpm

RUN yum-config-manager --enable remi,remi-php56
RUN yum install -y php php-common php-mysql

#Set service to start on server boot
RUN chkconfig mysqld on
RUN chkconfig httpd on

EXPOSE 80 443 3306 8000 8080

COPY scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash