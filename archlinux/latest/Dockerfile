FROM archlinux/base:latest
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN pacman -Sy --ask=20 --noconfirm --noprogressbar --needed \
    ccache \
    clang \
    llvm \
    gcc && \
    pacman -Scc --ask=20 --noconfirm
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

ENV PATH="/usr/lib/ccache/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

VOLUME [ "/ccache" ]
