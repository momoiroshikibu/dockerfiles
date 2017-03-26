FROM ubuntu:17.04

ENV JULIUS_VERSION 4.4.2.1
ENV JULIUS_DICTATION_KIT_VERSION 4.4

RUN apt-get update && apt-get install -y curl build-essential && apt-get clean

# julius
RUN curl -sL https://github.com/julius-speech/julius/archive/v$JULIUS_VERSION.tar.gz | tar -xvzf - && cd julius-$JULIUS_VERSION && ./configure && make && make install

# dictation kit
RUN mkdir -p /opt/julius && curl -sL https://github.com/julius-speech/dictation-kit/archive/v$JULIUS_DICTATION_KIT_VERSION.tar.gz | tar -C /opt/julius -xvzf -
