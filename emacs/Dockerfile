FROM ubuntu:16.10

RUN apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y git python ruby curl

# evm
RUN curl -fsSkL https://raw.github.com/rejeep/evm/master/go | bash
ENV PATH /root/.evm/bin:$PATH

# emacs 25.1
RUN evm config path /tmp
RUN evm install emacs-25.1-travis --use
RUN emacs --version

# cask
RUN curl -fsSL https://raw.githubusercontent.com/cask/cask/master/go | python
ENV PATH /root/.cask/bin:$PATH

# .emacs.d
RUN ls -la /tmp
WORKDIR /tmp
RUN git clone https://github.com/momoiroshikibu/dotEmacs.git
RUN mv /tmp/dotEmacs/* /root/.emacs.d

WORKDIR /root/.emacs.d
RUN cask install
RUN # emacs -batch -f batch-byte-compile init.el && \
    emacs -batch -f batch-byte-compile inits/*.el
RUN mkdir -p .auto-save-list && \
    mkdir -p .backups && \
    mkdir -p .cache/auto-complete && \
    mkdir -p .cache/recentf && \
    mkdir -p .cache/savehist

