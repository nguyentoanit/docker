FROM debian:stretch
MAINTAINER nguyentoanit
#Update repository and install necessary packages
RUN apt-get update -y
RUN apt-get install -y apache2 mysql-client mysql-server php cron php-pdo php-mysql php-common php-mbstring php-xml sudo curl vim nano composer build-essential libssl-dev

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
