
FROM ubuntu:16.04

RUN apt-get update && apt-get install -y gcc g++ netbase
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

ENV LANG en_US.utf8

RUN /usr/sbin/useradd -d /opt/ecloud -c "" "eacmuser"
ADD   ecloud.tar.gz /
COPY rules /opt/ecloud/rules

# cm agent port
EXPOSE 8030
# cm agent secure port
EXPOSE 8031
#db
EXPOSE 3306
# http port
EXPOSE 80
#erunner port
#EXPOSE 2411
#https
EXPOSE  443

CMD ["/opt/ecloud/rules/auto"]
