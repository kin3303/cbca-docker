
FROM  centos 
RUN  yum -y update &&  yum -y install epel-release  gcc gcc-c++.x86_64  ;  yum clean all
ADD  ecloud.tar.gz /
COPY rules /opt/ecloud/rules
CMD ["/opt/ecloud/rules/auto"]
