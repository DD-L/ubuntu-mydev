# ubuntu-mydev
# docker build -t="deel/ubuntu-mydev:14.04.4" .
# Author: Deel
FROM docker.io/ubuntu:14.04.4

MAINTAINER deel deel@d-l.top

#WORKDIR /opt

COPY ./etc/apt/apt.conf.d/02allow-unsigned /etc/apt/apt.conf.d/02allow-unsigned

# Commands to update the image
RUN Utilities='dos2unix wget git vim lsof' \
        && set -x \
        && apt-get install -y software-properties-common --no-install-recommends \
        && add-apt-repository -y ppa:ubuntu-toolchain-r/test \
        && apt-get update \
        && apt-get install -y gcc-4.9 g++-4.9 gdb make --no-install-recommends \
        && ln -s /usr/bin/g++-4.9 /usr/bin/g++ -f \
        && ln -s /usr/bin/gcc-4.9 /usr/bin/gcc -f \
        && ln -s /usr/bin/gcc-4.9 /usr/bin/cc -f \
        && ln -s /usr/bin/python3 /usr/bin/python -f \
        && apt-get install -y  --no-install-recommends \
        && apt-get autoclean \
        && apt-get clean \
        && apt-get autoremove \
        && rm -r /var/lib/apt/lists/*

# Commands when creating a new container
#CMD 
