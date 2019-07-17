FROM mageia:6
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-5.5.0-1.mga6 \
    clang-3.9.1-4.mga6 \
    ccache-3.3.4-1.mga6 && \
    dnf clean all && \
    rm -rf /var/cache/dnf
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib64/ccache/bin:/usr/local/sbin:/usr/sbin:/usr/local/bin:/usr/bin"

VOLUME [ "/ccache" ]
