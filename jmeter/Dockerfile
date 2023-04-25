FROM bash:4
LABEL MAINTAINER xcbeyond

ENV VERSION="5.5"

RUN set -ex ; \
  apk --no-cache add ca-certificates curl;

RUN curl -L https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-{VERSION}.zip -o apache-jmeter.zip; \
  tar -xvf apache-jmeter.zip;

CMD ["sh","-c","./apache-jmeter/bin/jmeter-server"]