FROM ubuntu:16.04
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gcc=4:5.3.1-1ubuntu1 \
    g++=4:5.3.1-1ubuntu1 \
    clang=1:3.8-33ubuntu3.1 \
    ccache=3.2.4-1 \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    ln -s /usr/bin/ccache /usr/local/bin/clang && \
    ln -s /usr/bin/ccache /usr/local/bin/clang++ && \
    ln -s /usr/bin/ccache /usr/local/bin/gcc && \
    ln -s /usr/bin/ccache /usr/local/bin/g++ && \
    ln -s /usr/bin/ccache /usr/local/bin/cc && \
    ln -s /usr/bin/ccache /usr/local/bin/c++ && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
