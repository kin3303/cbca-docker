
FROM  centos 
RUN yum -y update; yum clean all
RUN yum -y install epel-release gcc gcc-c++.x86_64; yum clean all
ADD ecloud.tar.gz /
ADD labs.tar.gz /tmp
COPY rules /opt/ecloud/rules
CMD ["/opt/ecloud/rules/auto"]
