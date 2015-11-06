FROM jolokia/java-jolokia:7

MAINTAINER deppisch@consol.de

EXPOSE 61616 8161 61613 1883 61614 5672

ENV BROKER_VERSION 5.12.0

# Get and Unpack
RUN curl  --output /opt/apache-activemq.zip http://central.maven.org/maven2/org/apache/activemq/apache-activemq/${BROKER_VERSION}/apache-activemq-${BROKER_VERSION}-bin.zip
RUN unzip /opt/apache-activemq.zip

# Add config
ADD activemq-conf.xml /opt/apache-activemq-${BROKER_VERSION}/conf/

# Remove unneeded files
RUN rm /opt/apache-activemq.zip
RUN rm -rf /opt/apache-activemq-${BROKER_VERSION}/examples
RUN rm -rf /opt/apache-activemq-${BROKER_VERSION}/docs
RUN rm -rf /opt/apache-activemq-${BROKER_VERSION}/webapps-demo

VOLUME ["/opt/apache-activemq-${BROKER_VERSION}/data"]

ENV ACTIVEMQ_HOME /opt/apache-activemq-${BROKER_VERSION}
ENV PATH $PATH:$ACTIVEMQ_HOME/bin

CMD /opt/apache-activemq-${BROKER_VERSION}/bin/activemq start xbean:conf/activemq-conf.xml
