# https://github.com/oracle/docker-images/blob/main/OracleInstantClient/oraclelinux8/21/Dockerfile
FROM oraclelinux:8

RUN  dnf -y install oracle-instantclient-release-el8 && \
     dnf -y install oracle-instantclient-basic oracle-instantclient-devel oracle-instantclient-sqlplus && \
     dnf -y install ansible-7.6.0 && \
     dnf -y install ansible-core-2.14.6 && \
     rm -rf /var/cache/dnf

# Uncomment if the tools package is added
# ENV PATH=$PATH:/usr/lib/oracle/21/client64/bin

CMD ["sqlplus", "-v"]