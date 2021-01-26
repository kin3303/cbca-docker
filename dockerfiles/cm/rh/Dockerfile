
FROM  yjjy0921/redhat7.2
RUN  /usr/sbin/useradd -d /opt/ecloud -c "" "eacmuser" ;  /usr/sbin/groupadd nogroup
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
