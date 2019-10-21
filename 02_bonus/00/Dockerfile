FROM ubuntu

LABEL maintainer="sskinner <sskinner@student.42.fr>"

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install sudo vim gcc -y
RUN mkdir /usr/Projects
WORKDIR /usr/Projects