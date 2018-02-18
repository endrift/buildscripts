FROM ubuntu:xenial

RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential bzip2 \
        ca-certificates curl git libfreeimage-dev libmpc-dev libmpfr-dev \
        libgmp-dev libudev-dev libusb-1.0.0-dev libz-dev make pkg-config \
        texinfo && \
    apt-get autoremove -y && apt-get clean

RUN mkdir -p /opt/archives /opt/devkitPro/devkitARM
COPY config.sh /root

ENV DEVKITPRO=/opt/devkitPro
ENV DEVKITARM=/opt/devkitPro/devkitARM
VOLUME /root/buildscripts
VOLUME /opt
WORKDIR /root/buildscripts
CMD cp /root/config.sh . && mkdir -p /opt/archives && ./build-devkit.sh
