FROM ubuntu:17.04

ENV JULIUS_VERSION v4.4.2.1
ENV JULIUS_DICTATION_KIT_VERSION dictation-kit-v4.3.1

RUN apt-get update && apt-get install -y curl build-essential && apt-get clean

# julius
RUN curl -sL https://github.com/julius-speech/julius/archive/$JULIUS_VERSION.tar.gz | tar -xvzf - && cd julius-$JULIUS_VERSION && ./configure && make && make install

# dictation kit
RUN mkdir -p /opt/julius && curl -sL https://github.com/julius-speech/dictation-kit/archive/$JULIUS_DICTATION_KIT_VERSION.tar.gz | tar -C /opt/julius -xvzf -
