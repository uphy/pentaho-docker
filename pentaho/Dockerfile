FROM openjdk:8

WORKDIR /usr/src
RUN curl -o pentaho.zip https://superb-sea2.dl.sourceforge.net/project/pentaho/Business%20Intelligence%20Server/7.0/pentaho-server-ce-7.0.0.0-25.zip
RUN unzip pentaho.zip && \
    rm -f pentaho.zip && \
    rm -f pentaho-server/promptuser.sh && \
    sed -i -e 's/\(exec ".*"\) start/\1 run/' pentaho-server/tomcat/bin/startup.sh

EXPOSE 8080
VOLUME /usr/src/pentaho-server/data

WORKDIR /usr/src/pentaho-server
CMD ./start-pentaho.sh