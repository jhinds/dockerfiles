FROM alpine

MAINTAINER Jonathan Hinds <jonathan.a.hinds@gmail.com>

RUN apk update && apk add \
    bash \
    && rm -rf /var/cache/apk/*

ENTRYPOINT ["bash"]
