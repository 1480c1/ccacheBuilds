FROM centos:6
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN yum install -y \
    epel-release-6-8 && \
    yum install -y \
    gcc-4.4.7-23.el6 \
    gcc-c++-4.4.7-23.el6 \
    clang-3.4.2-4.el6 \
    ccache-3.1.6-2.el6 && \
    yum clean all && \
    rm -rf /var/cache/yum
RUN ln -s /usr/bin/ccache /usr/local/bin/clang
RUN ln -s /usr/bin/ccache /usr/local/bin/clang++
RUN mkdir /root/.ccache/
RUN ln -s /root/.ccache/ /ccache

VOLUME [ "/ccache" ]
