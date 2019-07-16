FROM oraclelinux:6
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN yum install -y \
    gcc-4.4.7-23.0.1.el6 \
    gcc-c++-4.4.7-23.0.1.el6 \
    tar-1.23-15.el6_8 && \
    curl -Lo ccache.tar.gz "https://github.com/ccache/ccache/releases/download/v3.7.1/ccache-3.7.1.tar.gz" && \
    tar -xf ccache.tar.gz && \
    rm ccache.tar.gz && \
    bash -lc 'cd /ccache-3.7.1 && \
    ./configure --disable-man --with-bundled-zlib --prefix=/usr && \
    make -j 4 && \
    make install' &&\
    rm -rf ccache-3.7.1 && \
    ln -s /usr/bin/ccache /usr/local/bin/gcc && \
    ln -s /usr/bin/ccache /usr/local/bin/g++ && \
    ln -s /usr/bin/ccache /usr/local/bin/cc && \
    ln -s /usr/bin/ccache /usr/local/bin/c++ && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache && \
    yum erase -y \
    tar && \
    yum clean all && \
    rm -rf /var/cache/yum

VOLUME [ "/ccache" ]
