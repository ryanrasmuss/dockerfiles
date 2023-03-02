# dev
# ===
#
# My Development / Tinkering Container Environment
#
# Requires ...
#
# Build via
# docker build -t dev .
#
# Run via
# docker run -ti -v local/dir/on/host:/home/dev/ dev:latest
# 
# alias dev='docker run -ti -v $(``pwd``)/:/home/dev/ dev:latest'

# Base image debian
FROM debian:11

# Label base
LABEL dev latest

# Build on a volume to minimize space used (radare2 folks are smart)
VOLUME ["/mnt"]

# Install and build everything
# dkpg --add-architecture i386
# Cleanup
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    gcc \
    git \
    pkg-config \
    make \
    unzip \
    vim \
    ssh \
    net-tools \
    nmap \
    sudo \
    python3 \
    python3-pip && \
    pip3 install flask && \
    pip3 install requests && \
    apt-get autoremove --purge -y && \
    apt-get clean

# create working directory
WORKDIR /home/dev
ENV HOME /home/dev

# Base command for environment
CMD ["/bin/bash"]
