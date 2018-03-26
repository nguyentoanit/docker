FROM ubuntu:17.10
MAINTAINER docker@nguyentoanit

RUN apt-get update -y && apt-get install cron -y

# Run the command on container startup
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash
