FROM registry.access.redhat.com/ubi8/ubi:8.3
MAINTAINER sig-platform@spinnaker.io
COPY echo-web/build/install/echo /opt/echo
RUN yum -y install java-11-openjdk-headless.x86_64 wget vim curl net-tools nettle tzdata-java
RUN yum -y update
RUN adduser spinnaker
RUN mkdir -p /opt/echo/plugins
ARG CUSTOMPLUGIN_RELEASEVERSION
ENV CUSTOMPLUGIN_RELEASEVERSION=$CUSTOMPLUGIN_RELEASEVERSION
RUN wget -O Opsmx.EchoEventPlugin-EchoEventPlugin-v1.0.1-SNAPSHOT.zip -c https://github.com/OpsMx/Customplugins/releases/download/${CUSTOMPLUGIN_RELEASEVERSION}/EchoEventPlugin-v1.0.1-SNAPSHOT.zip -P /opt/echo/plugins
RUN mv Opsmx.EchoEventPlugin-EchoEventPlugin-v1.0.1-SNAPSHOT.zip /opt/echo/plugins/
RUN chmod -R 777 /opt/echo/plugins/
RUN chown -R spinnaker:spinnaker /opt/
USER spinnaker
CMD ["/opt/echo/bin/echo"]
