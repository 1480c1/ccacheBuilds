FROM amazonlinux:2
LABEL maintainer="Christopher Degawa <ccom@randomderp.com>" \
    name="ccacheBuilds" \
    description="ccache container for ci" \
    vcs-url="https://github.com/1480c1/ccacheBuilds" \
    License="MIT License" \
    version="0.0.1"

RUN yum install -y \
    tar-1.26-34.amzn2 \
    gzip-1.5-10.amzn2 \
    make-3.82-23.amzn2.0.2 \
    clang-7.0.1-1.amzn2.0.2 \
    gcc-7.3.1-5.amzn2.0.2 \
    gcc-c++-7.3.1-5.amzn2.0.2 &&\
    curl -Lo ccache.tar.gz "https://github.com/ccache/ccache/releases/download/v3.7.1/ccache-3.7.1.tar.gz" && \
    tar -xf ccache.tar.gz && \
    rm ccache.tar.gz && \
    bash -lc 'cd /ccache-3.7.1 && \
    ./configure --disable-man --with-bundled-zlib --prefix=/usr && \
    make -j 4 && \
    make install' && \
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
    tar \
    gzip \
    make && \
    yum clean all && \
    rm -rf /var/cache/yum

VOLUME [ "/ccache" ]
