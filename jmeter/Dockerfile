FROM bash:4
LABEL MAINTAINER xcbeyond

RUN set -ex ; \
  apk --no-cache add ca-certificates curl;

RUN curl -L https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-5.5.tgz -o apache-jmeter.tgz; \
  tar -zxvf apache-jmeter.tgz;

CMD ["sh","-c","./apache-jmeter/bin/jmeter-server"]