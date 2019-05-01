FROM debian

EXPOSE 8897/udp 10011/tcp 30033/tcp

RUN DEBIAN_FRONTEND=noninteractive
RUN apt update -yq && \
apt upgrade -yq && \
apt install -yq bzip2 wget

ADD https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2 ./

RUN tar xfvj teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN mv teamspeak3-server_linux_amd64 /opt/teamspeak
RUN rm teamspeak3-server_linux_amd64-3.6.1.tar.bz2

ENV TS3SERVER_LICENSE accept
ADD entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

#docker run -it --rm -p=9987:9987/udp  -p=10011:10011 -p=30033:30033 CONTAINER_IMAGE
