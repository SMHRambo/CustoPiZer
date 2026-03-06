# syntax=docker/dockerfile:1
ARG VERSION="trixie"
FROM debian:${VERSION}
ARG VERSION

ENV PACKAGES="binfmt-support \
    build-essential \
    fdisk \
    lsof \
    qemu-system \
    qemu-user-static \
    sudo \
    util-linux"

RUN set -ex \
    && apt-get update \
    && apt-get upgrade --yes \
    && apt-get install --no-install-recommends --yes ${PACKAGES} \
    && apt-get autoremove \
    && rm -rf /var/lib/apt/lists/*

COPY . /CustoPiZer

ENTRYPOINT [ "/bin/bash" ]
CMD [ "/CustoPiZer/customize" ]
