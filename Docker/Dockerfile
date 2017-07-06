FROM openjdk:8u111-jdk-alpine

MAINTAINER DL-SDP-GW-Microservice.dus@vodafone.com

# setup group and user, initialize home
RUN addgroup -g 30002 mspc-ms && \
    adduser -h /app -S -s /sbin/nologin -u 30002 mspc-ms

COPY mspc-ms.jar /app

RUN chown -R mspc-ms /app

# 8000 = debug port
# 8080 = api port
# 9080 = management port
EXPOSE 8000 8080 9080

USER mspc-ms
WORKDIR app

CMD ["java", \
 "-jar", \
 "./mspc-ms.jar"]