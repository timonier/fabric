FROM alpine:3.4

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    CUISINE_VERSION=0.7.13 \
    FABRIC_VERSION=1.11.1

RUN set -x \

    # Install packages

    && apk add --no-cache --no-progress --virtual build_deps \
           build-base \
           curl \
           gmp-dev \
           python-dev \
           py-pip \

    && apk add --no-cache --no-progress \
           ca-certificates \
           python \

    # Install fabric

    && pip install \
           cuisine==${CUISINE_VERSION} \
           fabric==${FABRIC_VERSION} \

    # Install timonier/dumb-entrypoint

    && curl -sL "https://github.com/timonier/dumb-entrypoint/raw/master/bin/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s install \

    # Clean

    && apk del \
           build_deps

ENTRYPOINT [ "dumb-init" , "--" , "dumb-entrypoint" ]
