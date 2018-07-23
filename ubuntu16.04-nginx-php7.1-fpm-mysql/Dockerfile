FROM nguyentoanit/ubuntu-with-cron:16.04
MAINTAINER nguyentoanit
#Update repository
RUN apt update -y && apt upgrade -y
RUN apt install nginx software-properties-common language-pack-en-base -y

# Add PHP PPA
RUN LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php -y
RUN add-apt-repository ppa:nilarimogard/webupd8 -y && apt update -y && apt install launchpad-getkeys -y && launchpad-getkeys

# Install PHP and Mysql
RUN DEBIAN_FRONTEND=noninteractive apt install php7.1 php7.1-fpm php7.1-curl php7.1-mysql -yq && DEBIAN_FRONTEND=noninteractive apt -yq install mysql-server mysql-client

# Set Entrypoint
ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
