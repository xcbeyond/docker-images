FROM node:6.14
LABEL MAINTAINER xcbeyond

RUN npm install gitbook-cli -g;\
   gitbook -V; \
   npm install svgexport -g --unsafe-perm

CMD ["/bin/sh"]