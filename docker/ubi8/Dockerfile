FROM registry.access.redhat.com/ubi8/ubi:8.3
MAINTAINER sig-platform@spinnaker.io
COPY echo-web/build/install/echo /opt/echo
RUN yum -y install java-11-openjdk-headless.x86_64 wget vim curl net-tools nettle
RUN yum -y update
RUN adduser spinnaker
RUN mkdir -p /opt/echo/plugins
