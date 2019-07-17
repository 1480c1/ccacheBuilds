FROM fedora:27
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-7.3.1-6.fc27 \
    clang-5.0.2-1.fc27 \
    ccache-3.3.6-1.fc27 && \
    dnf clean all && \
    rm -rf /var/cache/dnf
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
