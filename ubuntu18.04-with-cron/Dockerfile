#Ref: https://www.ekito.fr/people/run-a-cron-job-with-docker/
FROM ubuntu:18.04
MAINTAINER docker@nguyentoanit

CMD cron

# Run the command on container startup
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash
