FROM rabbitmq:management
MAINTAINER Chair of Software Engineering <se2-it@informatik.uni-wuerzburg.de>

COPY apache-tomcat-8.5.24.zip /apache.zip
COPY rabbitmq.config /etc/rabbitmq/
COPY custom_definitions.json /etc/rabbitmq/

RUN apt-get update
RUN apt-get install unzip
RUN unzip /apache.zip
RUN chmod -R +x /apache-tomcat-8.5.24
RUN mkdir /usr/share/man/man1
RUN apt-get -y install default-jre-headless

COPY target/tools.descartes.teastore.kieker.rabbitmq.war /apache-tomcat-8.5.24/webapps/logs.war

EXPOSE 8080

#Login for rabbitmq webui is admin:nimda
CMD  /apache-tomcat-8.5.24/bin/startup.sh && rabbitmq-server