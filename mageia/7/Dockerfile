FROM mageia:7
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-8.3.1-0.20190524.1.mga7 \
    clang-8.0.0-1.mga7 \
    ccache-3.7.1-1.mga7 && \
    dnf clean all && \
    rm -rf /var/cache/dnf
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib64/ccache/bin:/usr/local/sbin:/usr/sbin:/usr/local/bin:/usr/bin"

VOLUME [ "/ccache" ]
