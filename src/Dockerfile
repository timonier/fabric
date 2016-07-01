FROM alpine:3.4
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
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
           fabric==$FABRIC_VERSION \

    # Clean

    && apk del \
           build_deps

ENTRYPOINT [ "/usr/bin/fab" ]
