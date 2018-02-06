#Ref: https://www.ekito.fr/people/run-a-cron-job-with-docker/
FROM ubuntu:17.10
MAINTAINER docker@nguyentoanit

CMD apt-get update
CMD apt-get install cron -y

# Run the command on container startup
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash
