FROM ubuntu:17.04
MAINTAINER momoiroshikibu <momoiroshikibu@gmail.com>

RUN apt-get update \
    && apt-get upgrade -y

RUN apt-get install -y \
    build-essential \
    curl \
    autotools-dev \
    automake \
    libcurl4-gnutls-dev

RUN curl -SL https://github.com/snmsts/roswell/archive/release.tar.gz \
    | tar -xzC /tmp/

WORKDIR /tmp/roswell-release
RUN sh bootstrap && ./configure && make && make install
RUN ros install sbcl-bin
