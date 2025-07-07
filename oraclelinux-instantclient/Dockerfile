# https://github.com/oracle/docker-images/blob/main/OracleInstantClient/oraclelinux8/21/Dockerfile
FROM oraclelinux:8

ARG release=19
ARG update=10

RUN  dnf -y install oracle-release-el8 && \
     dnf -y install oracle-instantclient${release}.${update}-basic oracle-instantclient${release}.${update}-devel oracle-instantclient${release}.${update}-sqlplus && \
     dnf -y install python27 && \
     rm -rf /var/cache/dnf

# Uncomment if the tools package is added
# ENV PATH=$PATH:/usr/lib/oracle/${release}.${update}/client64/bin

CMD ["sqlplus", "-v"]