ARG ALPINE_VERSION_NAME=latest

FROM alpine:${ALPINE_VERSION_NAME}

# Your Property
ARG USER=user
ARG USER_ID=1000
ARG GROUP_ID=1000

RUN apk update && apk add --no-cache perl sudo \
    && addgroup -g "${GROUP_ID}" "${USER}" \
    && adduser -D -u "${USER_ID}" -s /bin/sh -G "${USER}" "${USER}" \
    && adduser "${USER}" wheel \
    && echo '%wheel ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

USER ${USER}

# TMP Docker Volume
VOLUME ["/WORKDIR"]

WORKDIR /WORKDIR