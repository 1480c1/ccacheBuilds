FROM fedora:26
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-7.3.1-2.fc26 \
    clang-4.0.1-5.fc26 \
    ccache-3.3.6-1.fc26 && \
    dnf clean all && \
    rm -rf /var/cache/dnf
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
