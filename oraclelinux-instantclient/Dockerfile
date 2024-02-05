# https://github.com/oracle/docker-images/blob/main/OracleInstantClient/oraclelinux8/21/Dockerfile
FROM oraclelinux:8

RUN  dnf -y install oracle-instantclient-release-el8 && \
     dnf -y install oracle-instantclient-basic oracle-instantclient-devel oracle-instantclient-sqlplus && \
     dnf -y install python3.11 && \
     dnf -y install ansible && \
     dnf -y install ansible-core && \
     rm -rf /var/cache/dnf

# Uncomment if the tools package is added
# ENV PATH=$PATH:/usr/lib/oracle/21/client64/bin

CMD ["sqlplus", "-v"]