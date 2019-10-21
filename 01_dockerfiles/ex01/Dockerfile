FROM debian

LABEL maintainer="sskinner <sskinner@student.42.fr>"

ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10011 30033

RUN apt-get update && \
    apt-get upgrade -y && \
    apt install wget bzip2 -y && \
    wget http://dl.4players.de/ts/releases/3.8.0/teamspeak3-server_linux_amd64-3.8.0.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.8.0.tar.bz2

ENTRYPOINT sh /teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh

# https://unixblogger.com/setup-a-teamspeak-3-server-on-linux-ubuntu-debian/
# https://hub.docker.com/_/teamspeak for env
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01