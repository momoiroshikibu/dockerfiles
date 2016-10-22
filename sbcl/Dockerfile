FROM alpine:edge
MAINTAINER momoiroshikibu <momoiroshikibu@gmail.com>

RUN apk update \
    && apk upgrade \
    && apk add sbcl --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ --allow-untrusted
