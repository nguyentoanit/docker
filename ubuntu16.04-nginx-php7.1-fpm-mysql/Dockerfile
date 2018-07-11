FROM nguyentoanit/ubuntu-with-cron:16.04
MAINTAINER nguyentoanit
#Update repository
RUN apt update

#Set service to start on server boot
# RUN chkconfig httpd on

ADD scripts/start_service.sh /usr/local/bin/start_service.sh
ENTRYPOINT sh /usr/local/bin/start_service.sh;/bin/bash
