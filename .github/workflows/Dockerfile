FROM amazon/aws-cli:2.4.18
LABEL author="Maxim Generalov" \
  maintainer="maxim.generalov@sap.com"
USER root

# Install additional components
RUN yum install postgresql -y \
    yum clean all && \
    rm -rf /var/cache/yum