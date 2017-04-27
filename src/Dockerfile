FROM python:2-alpine

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    FABRIC_VERSION=latest

RUN set -eux \

    # Install packages

    && apk add --no-cache --no-progress --virtual BUILD_DEPS \
           build-base \
           curl \
           libffi-dev \
           openssl-dev \

    && apk add --no-cache --no-progress \
           ca-certificates \
           libffi \

    # Install dumb-entrypoint

    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/bin/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s install \

    # Install fabric

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/fabric/${FABRIC_VERSION}" | xargs) \

    && pip install \
           cuisine \
           "fabric==${FABRIC_VERSION}" \

    # Clean

    && apk del \
           BUILD_DEPS \

    && rm -f -r \
         /root/.cache \
         /tmp/*

ENTRYPOINT [ "dumb-init" , "--" , "dumb-entrypoint" ]
