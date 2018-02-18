FROM ubuntu:xenial

RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential bzip2 \
        ca-certificates ccache curl git libfreeimage-dev libgl-dev libmpc-dev \
        libmpfr-dev libgmp-dev libz-dev make pkg-config texinfo && \
    apt-get autoremove -y && apt-get clean

RUN mkdir -p /opt/archives /opt/devkitPro/devkitPPC
COPY config.sh /root

ENV DEVKITPRO=/opt/devkitPro
ENV DEVKITPPC=/opt/devkitPro/devkitPPC
ENV PATH=/usr/lib/ccache:$PATH
VOLUME /root/buildscripts
VOLUME /opt
WORKDIR /root/buildscripts
CMD cp /root/config.sh . && mkdir -p /opt/archives && ./build-devkit.sh
