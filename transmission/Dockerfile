FROM armhf/alpine:latest

ADD ./config/ /config/

RUN apk update && \
apk add transmission-daemon && \
mkdir /download && \
chown -R transmission.transmission /config

EXPOSE 9091

USER transmission
WORKDIR /home/transmission

VOLUME ["/download"]

ENTRYPOINT ["/usr/bin/transmission-daemon", "--foreground", "--config-dir", "/config/"]

