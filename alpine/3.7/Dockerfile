FROM alpine:3.7
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN apk add --no-progress --no-cache \
    ccache=3.3.4-r0 \
    clang-dev=5.0.0-r0 \
    gcc=6.4.0-r5 \
    g++=6.4.0-r5
RUN ln -s /usr/bin/ccache /usr/local/bin/clang
RUN ln -s /usr/bin/ccache /usr/local/bin/clang++
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib/ccache/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

VOLUME [ "/ccache" ]
