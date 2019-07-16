FROM centos:7.6.1810
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN yum install -y \
    epel-release-7-11 && \
    yum install -y \
    clang-3.4.2-9.el7 \
    gcc-4.8.5-36.el7_6.2 \
    gcc-c++-4.8.5-36.el7_6.2 \
    ccache-3.3.4-1.el7 && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache && \
    yum clean all && \
    rm -rf /var/cache/yum

VOLUME [ "/ccache" ]
