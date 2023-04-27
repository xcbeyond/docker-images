FROM openjdk:8
LABEL MAINTAINER xcbeyond

RUN curl -L -k https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-5.5.tgz -o apache-jmeter-5.5.tgz; \
  tar -zxvf apache-jmeter-5.5.tgz; \
  curl -L https://raw.githubusercontent.com/xcbeyond/docker-images/master/jmeter/jmeter.properties -o ./apache-jmeter-5.5/bin/jmeter.properties;

EXPOSE 1099

CMD ["/bin/bash","-c","./apache-jmeter-5.5/bin/jmeter-server"]