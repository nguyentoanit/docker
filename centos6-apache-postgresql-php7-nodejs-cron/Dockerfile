FROM centos:6.9
MAINTAINER nguyentoanit
#Update repository
RUN yum update -y
RUN yum install -y epel-release yum-utils httpd sudo postgresql postgresql-server crontabs git curl zip unzip https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm http://rpms.remirepo.net/enterprise/remi-release-6.rpm

#Install PHP repository
RUN yum-config-manager --enable remi-php72

RUN curl --silent --location https://rpm.nodesource.com/setup_9.x | sudo bash -

#Install neccessary packages
RUN yum install -y php php-common php-pgsql php-pdo php-mbstring php-xml nodejs

#Install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN sudo mv composer.phar /usr/local/bin/composer

#Set service to start on server boot
RUN chkconfig postgresql on
RUN chkconfig httpd on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
