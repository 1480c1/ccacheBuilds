FROM ubuntu:19.04
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gcc=4:8.3.0-1ubuntu3 \
    g++=4:8.3.0-1ubuntu3 \
    clang=1:8.0-48~exp1ubuntu1 \
    ccache=3.6-1 \
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
