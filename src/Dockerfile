FROM alpine:3.4
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    CUISINE_VERSION=0.7.13 \
    FABRIC_VERSION=1.11.1

RUN set -x \

    # Install packages

    && apk add --no-cache --no-progress --virtual build_deps \
           build-base \
           gmp-dev \
           python-dev \
           py-pip \

    && apk add --no-cache --no-progress \
           python \

    # Install fabric

    && pip install \
           cuisine==$CUISINE_VERSION \
           fabric==$FABRIC_VERSION \

    # Clean

    && apk del \
           build_deps

ENTRYPOINT [ "/usr/bin/fab" ]
