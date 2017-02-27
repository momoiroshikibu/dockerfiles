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

RUN curl -SL "https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7cENtOXlicTFaRUE" \
    | tar -xzC /tmp/

WORKDIR /tmp/mecab-0.996
RUN ./configure --enable-utf8-only; make; make install; ldconfig


RUN curl -SL "https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7MWVlSDBCSXZMTXM" \
    | tar -xzC /tmp/
WORKDIR /tmp/mecab-ipadic-2.7.0-20070801
RUN ./configure --with-charset=utf8; make; make install

