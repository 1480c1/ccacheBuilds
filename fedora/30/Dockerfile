FROM fedora:30
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN dnf install -y \
    gcc-9.1.1-1.fc30 \
    clang-8.0.0-1.fc30 \
    ccache-3.4.3-2.fc30 && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache && \
    dnf clean all && \
    rm -rf /var/cache/dnf

VOLUME [ "/ccache" ]
