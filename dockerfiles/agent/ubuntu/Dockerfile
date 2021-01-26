FROM ubuntu:16.04
RUN apt-get update && apt-get install -y gcc g++ netbase
ADD ecloud.tar.gz /
COPY rules /opt/ecloud/rules
CMD ["/opt/ecloud/rules/auto"]
