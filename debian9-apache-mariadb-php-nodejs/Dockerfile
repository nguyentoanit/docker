FROM debian:stretch
MAINTAINER nguyentoanit
#Update repository and install necessary packages
RUN apt-get update
RUN apt-get install -y apache2 mysql-client mysql-server php cron php-pdo php-mysql php-common php-mbstring php-xml sudo curl vim nano composer build-essential libssl-dev

#Install Node JS
#RUN curl -sL https://deb.nodesource.com/setup_9.x | sudo bash -
#RUN apt-get install -y nodejs

#ADD scripts/install_nvm.sh /usr/local/bin/install_nvm.sh
#ADD scripts/install_nodejs_npm.sh /usr/local/bin/install_nodejs_npm.sh
#RUN sh /usr/local/bin/install_nvm.sh
#RUN sh /usr/local/bin/install_nodejs_npm.sh

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
