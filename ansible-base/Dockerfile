FROM ubuntu:22.04
LABEL MAINTAINER xcbeyond

# install ansible
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
       passlib==1.7.4

# install mysql command
RUN apt-get install -y mysql-client \
    && apt-get install -y unzip

# install sqlplus
RUN apt-get update && \
    apt-get install -y libaio1 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    mkdir -p /opt/oracle && \
    curl -L https://download.oracle.com/otn_software/linux/instantclient/211000/instantclient-basiclite-linux.x64-21.1.0.0.0.zip -o /opt/oracle/instantclient-basiclite-linux.x64.zip && \
    unzip /opt/oracle/instantclient-basiclite-linux.x64.zip -d /opt/oracle && \
    rm /opt/oracle/instantclient-basiclite-linux.x64.zip && \
    ln -s /opt/oracle/instantclient* /usr/lib && \
    echo "/opt/oracle/instantclient_21_1" > /etc/ld.so.conf.d/oracle-instantclient.conf && \
    ldconfig

# Set environment variables for Oracle Instant Client
ENV LD_LIBRARY_PATH="/opt/oracle/instantclient_21_1:${LD_LIBRARY_PATH}"

# Cleanup
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
