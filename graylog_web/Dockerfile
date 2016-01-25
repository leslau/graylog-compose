FROM java:7

MAINTAINER Micah Hausler, micah.hausler@ambition.com

ENV GRAYLOGWEB_VERSION 1.3.3

ADD https://packages.graylog2.org/releases/graylog2-web-interface/graylog-web-interface-$GRAYLOGWEB_VERSION.tgz /opt/

RUN cd /opt/ \
    && tar xfz graylog-web-interface-$GRAYLOGWEB_VERSION.tgz \
    && mv graylog-web-interface-$GRAYLOGWEB_VERSION graylog \
    && rm graylog-web-interface-$GRAYLOGWEB_VERSION.tgz

EXPOSE 9443

WORKDIR /opt/graylog
CMD /opt/graylog/bin/graylog-web-interface -Dhttps.port=9443
