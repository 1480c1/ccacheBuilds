FROM amazonlinux:1
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN yum install -y \
    findutils-4.4.2-6.9.amzn1 \
    clang-3.6.2-1.12.amzn1 \
    gcc-4.8.5-1.22.amzn1 \
    gcc-c++-4.8.5-1.22.amzn1 && \
    curl -Lo ccache.tar.gz "https://github.com/ccache/ccache/releases/download/v3.7.1/ccache-3.7.1.tar.gz" && \
    tar -xf ccache.tar.gz && \
    rm ccache.tar.gz && \
    bash -lc 'cd /ccache-3.7.1 && \
    ./configure --disable-man --with-bundled-zlib --prefix=/usr && \
    make -j 4 && \
    make install' &&\
    rm -rf ccache-3.7.1 && \
    ln -s /usr/bin/ccache /usr/local/bin/clang && \
    ln -s /usr/bin/ccache /usr/local/bin/clang++ && \
    ln -s /usr/bin/ccache /usr/local/bin/gcc && \
    ln -s /usr/bin/ccache /usr/local/bin/g++ && \
    ln -s /usr/bin/ccache /usr/local/bin/cc && \
    ln -s /usr/bin/ccache /usr/local/bin/c++ && \
    mkdir /root/.ccache/ && \
    ln -s /root/.ccache/ /ccache && \
    yum erase -y \
    findutils && \
    yum clean all && \
    rm -rf /var/cache/yum

VOLUME [ "/ccache" ]
