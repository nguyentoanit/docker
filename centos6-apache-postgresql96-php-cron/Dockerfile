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

#Install PostgreSQL 9.6 repository
RUN yum install -y https://download.postgresql.org/pub/repos/yum/9.6/redhat/rhel-6-x86_64/pgdg-centos96-9.6-3.noarch.rpm

#Install neccessary packages
RUN yum --enablerepo=remi install -y php php-common php-pgsql php-pdo php-mbstring php-xml

RUN yum install -y postgresql96-server postgresql96
#RUN service postgresql-9.6 initdb

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

#Set service to start on server boot
RUN chkconfig postgresql-9.6 on
RUN chkconfig httpd on

#EXPOSE 80 443 5432 8000 8080

COPY scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash