#Ref: https://www.ekito.fr/people/run-a-cron-job-with-docker/
FROM ubuntu:14.04
MAINTAINER docker@nguyentoanit

# Give execution rights on the cron job
RUN chmod 0644 -R /etc/cron.d

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

CMD cron

# Run the command on container startup
ENTRYPOINT /usr/local/bin/start_service.sh;/bin/bash
