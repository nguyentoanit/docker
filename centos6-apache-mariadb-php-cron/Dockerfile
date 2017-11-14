FROM centos:6.8
MAINTAINER nguyentoanit
#Update repository
RUN yum update --exclude=centos-release -y
RUN yum install epel-release -y
RUN yum --enablerepo=extras install  centos-release-scl -y

#Install crontab
RUN yum install -y crontabs yum-utils httpd git

#Install PHP repository
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN yum-config-manager --enable remi,remi-php56

#Install MariaDB repository
COPY config/MariaDB.repo /etc/yum.repos.d/MariaDB.repo

#Install neccessary packages
RUN yum --enablerepo=remi install -y php php-common php-mysqlnd php-pdo php-mbstring
RUN yum install -y MariaDB-server MariaDB-client

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

#Set service to start on server boot
RUN chkconfig mysql on
RUN chkconfig httpd on

#EXPOSE 80 443 3306 8000 8080

COPY scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash