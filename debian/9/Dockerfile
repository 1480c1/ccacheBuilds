FROM debian:9
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gcc=4:6.3.0-4 \
    g++=4:6.3.0-4 \
    clang=1:3.8-36 \
    ccache=3.3.4-1 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
RUN update-alternatives --install /usr/local/bin/cc cc /usr/bin/ccache  100
RUN update-alternatives --install /usr/local/bin/c++ c++ /usr/bin/ccache  100
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib/ccache:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

VOLUME [ "/ccache" ]
