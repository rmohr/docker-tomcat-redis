FROM tutum/tomcat:7.0
MAINTAINER Roman Mohr <roman@fenkhuber.at>

ENV REDIS_HOST redis
ENV REDIS_PORT 6379

RUN \
    cd /tomcat/lib && \
    wget -q  https://github.com/rmohr/tomcat-redis-session-manager/releases/download/2.0-tomcat-7/tomcat-redis-session-manager-2.0.0.jar && \
    wget -q http://central.maven.org/maven2/redis/clients/jedis/2.5.2/jedis-2.5.2.jar && \
    wget -q http://central.maven.org/maven2/org/apache/commons/commons-pool2/2.2/commons-pool2-2.2.jar

COPY run-with-redis.sh run-with-redis.sh
RUN chmod +x /*.sh
CMD ["/run-with-redis.sh"]
