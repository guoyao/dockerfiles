FROM centos:centos7.7.1908

ENV NODE_VERSION 10.18.0

RUN yum install -y git wget \
    && wget https://nodejs.org/dist/latest-v10.x/node-v$NODE_VERSION-linux-x64.tar.gz \
    && tar zxf node-v$NODE_VERSION-linux-x64.tar.gz -C /usr/local \
    && rm -f node-v$NODE_VERSION-linux-x64.tar.gz \
    && ln -s /usr/local/node-v$NODE_VERSION-linux-x64/bin/node /usr/local/bin/node \
    && ln -s /usr/local/node-v$NODE_VERSION-linux-x64/bin/npm /usr/local/bin/npm

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "node" ]
