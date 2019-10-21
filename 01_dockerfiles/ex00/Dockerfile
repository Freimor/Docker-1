FROM alpine

LABEL maintainer="sskinner <sskinner@student.42.fr>"

RUN apk update && \
    apk upgrade && \
    apk add vim

ENTRYPOINT vim
#docker build -t -f