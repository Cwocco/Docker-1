# docker build -t ts3 .
# docker volume create --name teamspeak-storage
# docker run --name=teamspeak -d -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -v teamspeak-storage:/teamspeak3-server_linux_amd64/storage ts3

FROM debian

EXPOSE 9987/udp
EXPOSE 10011/tcp
EXPOSE 30033/tcp

ADD http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 /tmp

RUN apt-get update && apt-get install -y bzip2 && tar -xjvf /tmp/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 && useradd teamspeak && mkdir -p /teamspeak3-server_linux_amd64/storage  && chown teamspeak:teamspeak /teamspeak3-server_linux_amd64/storage

VOLUME /teamspeak3-server_linux_amd64/storage

USER teamspeak

CMD /teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start
