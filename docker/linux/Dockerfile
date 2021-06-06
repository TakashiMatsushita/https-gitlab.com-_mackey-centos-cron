FROM centos:latest

WORKDIR /project

RUN yum -y update && \
    yum -y install crontabs && \
    yum -y install sudo && \
    yum -y install curl && \
    yum -y install vim

RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime 

COPY cron/schedule /etc/cron.d/schedule

RUN chmod 644 /etc/cron.d/schedule && \
    chown root /etc/cron.d/schedule && \
    touch /tmp/schedule.log && \
    touch /tmp/schedule-error.log

COPY docker/linux/aliases.txt /project/docker/linux/aliases.txt
RUN cat /project/docker/linux/aliases.txt >> ~/.bashrc
