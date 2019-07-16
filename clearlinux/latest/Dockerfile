FROM clearlinux:base
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN swupd bundle-add \
    ccache \
    llvm \
    c-basic && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache && \
    swupd clean

VOLUME [ "/ccache" ]
