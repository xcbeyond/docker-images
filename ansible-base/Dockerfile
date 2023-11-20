FROM ubuntu:22.04
LABEL MAINTAINER xcbeyond

RUN apt-get update -q \
    && apt-get install -yq --no-install-recommends \
       curl \
       python3 \
       python3-pip \
       sshpass \
       vim \
       rsync \
       openssh-client \
    && pip install --no-compile --no-cache-dir \
       ansible==7.6.0 \
       ansible-core==2.14.6 \
       cryptography==41.0.1 \
       jinja2==3.1.2 \
       netaddr==0.8.0 \
       jmespath==1.0.1 \
       MarkupSafe==2.1.3 \
       ruamel.yaml==0.17.21 \
       passlib==1.7.4 \
   && apt-get install mysql-client