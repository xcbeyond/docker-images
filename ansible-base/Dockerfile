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

# install mikefarah/yq
RUN apt-get install -yq snapd \
    && snap install -y yq

# install mysql command
RUN apt-get install -y mysql-client \
    && apt-get install -y unzip

# install sqlplus
RUN apt-get update && \
    apt-get install -y libaio1 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    mkdir -p /opt/oracle && \
    curl -L https://download.oracle.com/otn_software/linux/instantclient/213000/instantclient-basic-linux-21.3.0.0.0.zip -o /opt/oracle/instantclient-basic-linux-21.3.0.0.0.zip && \
    curl -L https://download.oracle.com/otn_software/linux/instantclient/213000/instantclient-sqlplus-linux-21.3.0.0.0.zip -o /opt/oracle/instantclient-sqlplus-linux-21.3.0.0.0.zip && \
    unzip /opt/oracle/instantclient-basic-linux-21.3.0.0.0.zip -d /opt/oracle && \
    unzip /opt/oracle/instantclient-sqlplus-linux-21.3.0.0.0.zip -d /opt/oracle && \
    rm /opt/oracle/instantclient-basic-linux-21.3.0.0.0.zip /opt/oracle/instantclient-sqlplus-linux-21.3.0.0.0.zip

# Set environment variables for Oracle Instant Client
ENV LD_LIBRARY_PATH="/opt/oracle/instantclient_21_3"
ENV ORACLE_HOME=/opt/oracle/instantclient_21_3
ENV PATH=$PATH:$ORACLE_HOME
# 允许非交互式使用 SQL*Plus
ENV TWO_TASK=
# 指定 SQL*Plus 的字符集
ENV NLS_LANG=AMERICAN_AMERICA.UTF8

# Cleanup
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
