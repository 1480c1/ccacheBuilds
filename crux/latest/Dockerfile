FROM crux:3.4
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN ports -u && \
    prt-get install \
    ccache && \
    rm -rf /usr/ports/core
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib/ccache:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

VOLUME [ "/ccache" ]
