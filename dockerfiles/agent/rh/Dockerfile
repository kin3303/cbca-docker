FROM registry.access.redhat.com/rhel7
ADD ecloud.tar.gz /
ADD labs.tar.gz /tmp
COPY rules /opt/ecloud/rules
CMD ["/opt/ecloud/rules/auto"]
