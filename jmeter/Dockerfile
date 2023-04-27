FROM openjdk:8
LABEL MAINTAINER xcbeyond

RUN curl -L -k https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-5.5.tgz -o apache-jmeter-5.5.tgz; \
  tar -zxvf apache-jmeter-5.5.tgz; \
  curl -L https://github.com/xcbeyond/docker-images/blob/551ec492cd6b5fbb5700915ce698f1cd34dee97c/jmeter/jmeter.properties -o ./apache-jmeter-5.5/bin/jmeter.properties;

CMD ["/bin/bash","-c","./apache-jmeter-5.5/bin/jmeter-server"]