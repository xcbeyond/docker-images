FROM node:14-alpine

LABEL maintainer xcbeyond

ENV VERSION 1.9.2

RUN mkdir /yapi && \
    wget -O /yapi/yapi.tgz http://registry.npm.taobao.org/yapi-vendor/download/yapi-vendor-$VERSION.tgz && \
    tar zxvf /yapi/yapi.tgz -C /yapi  && mv /yapi/package /yapi/vendors
RUN cd /yapi/vendors && \
    npm install --production --registry https://registry.npm.taobao.org && \
    wget -O /yapi/config.json https://raw.githubusercontent.com/xcbeyond/docker-images/master/yapi/1.9.2/config.json && \
    wget -O /yapi/vendors/server/utils/commons.js https://raw.githubusercontent.com/xcbeyond/docker-images/master/yapi/1.9.2/commons.js && \
    wget -O /yapi/run.sh https://raw.githubusercontent.com/xcbeyond/docker-images/master/yapi/1.9.2/run.sh && chmod 777 /yapi/run.sh

# COPY config.json /yapi
# https://github.com/YMFE/yapi/issues/2231
# COPY commons.js /yapi/vendors/server/utils
# COPY run.sh /yapi
# RUN chmod 777 /yapi/run.sh

EXPOSE 3000
ENTRYPOINT ["/yapi/run.sh"]