FROM fedora:29
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-8.3.1-2.fc29 \
    clang-7.0.1-6.fc29 \
    ccache-3.4.2-4.fc29 && \
    dnf clean all && \
    rm -rf /var/cache/dnf
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
