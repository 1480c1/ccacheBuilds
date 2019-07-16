FROM crux:3.4
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN ports -u && \
    prt-get install \
    sqlite3 \
    expat \
    libffi \
    python \
    ninja \
    cmake \
    clang \
    ccache && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
