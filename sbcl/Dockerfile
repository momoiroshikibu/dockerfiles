FROM frolvlad/alpine-glibc
MAINTAINER momoiroshikibu <momoiroshikibu@gmail.com>

RUN apk update \
    && apk upgrade \
    && apk add sbcl --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ --allow-untrusted \
    && apk add curl autoconf automake gcc g++ make curl-dev

RUN curl -O https://github.com/snmsts/roswell/archive/release.tar.gz

RUN curl -SL https://github.com/snmsts/roswell/archive/release.tar.gz | tar -xzC /tmp/
RUN cd /tmp/roswell-release && sh bootstrap && ./configure && make && make install

RUN curl -O https://beta.quicklisp.org/quicklisp.lisp
