FROM quay.io/opsmxpublic/ubi8-jre-11:v1
MAINTAINER sig-platform@spinnaker.io
COPY echo-web/build/install/echo /opt/echo
RUN yum -y install java-11-openjdk-headless.x86_64 wget vim curl net-tools nettle
RUN yum -y update
RUN adduser spinnaker
RUN mkdir -p /opt/echo/plugins
RUN chmod -R 777 /opt/echo/plugins/
RUN chown -R spinnaker:spinnaker /opt/
USER spinnaker
CMD ["/opt/echo/bin/echo"]
