FROM java:7

MAINTAINER Micah Hausler, micah.hausler@ambition.com

ENV GRAYLOG_VERSION 1.3.3

ENV JAVA_HOME /opt/graylog/embedded/jre

ADD https://packages.graylog2.org/releases/graylog2-server/graylog-$GRAYLOG_VERSION.tgz /opt/

RUN cd /opt/ \
    && tar xfz graylog-$GRAYLOG_VERSION.tgz \
    && mv graylog-$GRAYLOG_VERSION/ graylog/ \
    && rm graylog-$GRAYLOG_VERSION.tgz \
    && mkdir -p /opt/graylog/embedded/jre/bin/ \
    && ln -s /usr/bin/java /opt/graylog/embedded/jre/bin/java

VOLUME /opt/graylog/plugin

# gelf tcp/udp
EXPOSE 12201
EXPOSE 12201/udp

# rest api
EXPOSE 12900

# syslog
EXPOSE 514
EXPOSE 514/udp

ENV TERM xterm

WORKDIR /opt/graylog
CMD /opt/graylog/bin/graylogctl run
