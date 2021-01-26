FROM ubuntu:16.04
RUN apt-get update && apt-get install -y gcc g++ netbase
ADD ecloud.tar.gz /
ADD labs.tar.gz /tmp
COPY rules /opt/ecloud/rules
CMD ["/opt/ecloud/rules/auto"]
