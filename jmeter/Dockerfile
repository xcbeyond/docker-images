FROM openjdk:8u121
LABEL MAINTAINER xcbeyond

RUN curl -L -k https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-5.5.tgz -o apache-jmeter-5.5.tgz; \
  tar -zxvf apache-jmeter-5.5.tgz;

CMD ["sh","-c","./apache-jmeter-5.5/bin/jmeter-server"]