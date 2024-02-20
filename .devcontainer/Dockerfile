FROM mcr.microsoft.com/devcontainers/cpp:1-debian-11

# [Optional] Uncomment this section to install additional vcpkg ports.
# RUN su vscode -c "${VCPKG_ROOT}/vcpkg install <your-port-name-here>"

# Install dependencies first
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
        automake \
        libtool \
        wget \
        m4 \
        perl \
        texinfo

# Install autoconf 2.72, automake 1.17, and libtool 2.5.4 from source to match maintainers' versions
RUN cd /tmp \
    && wget https://ftp.gnu.org/gnu/autoconf/autoconf-2.72.tar.xz \
    && tar -xf autoconf-2.72.tar.xz \
    && cd autoconf-2.72 \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd /tmp \
    && wget https://ftp.gnu.org/gnu/automake/automake-1.17.tar.xz \
    && tar -xf automake-1.17.tar.xz \
    && cd automake-1.17 \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd /tmp \
    && wget https://ftp.gnu.org/gnu/libtool/libtool-2.5.4.tar.xz \
    && tar -xf libtool-2.5.4.tar.xz \
    && cd libtool-2.5.4 \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd / \
    && rm -rf /tmp/autoconf-2.72* /tmp/automake-1.17* /tmp/libtool-2.5.4*
