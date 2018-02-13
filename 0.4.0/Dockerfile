FROM openjdk:8-jdk-alpine

ARG VERSION

ENV DIST_MIRROR     https://archive.apache.org/dist/nifi/minifi
ENV MINIFI_HOME     /opt/minifi
ENV VERSION         ${VERSION}

RUN set -x && \
    apk --no-cache add tar wget && \
	mkdir -p ${MINIFI_HOME} && \
	wget -qO- ${DIST_MIRROR}/${VERSION}/minifi-${VERSION}-bin.tar.gz | tar xvz -C ${MINIFI_HOME} --strip-components=1 && \
    addgroup minifi && \
    adduser -D -G minifi minifi && \
    chown -R minifi:minifi ${MINIFI_HOME}
	
USER minifi
WORKDIR ${MINIFI_HOME}

CMD ["bin/minifi.sh","run"]