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

# Base image debian 9
FROM debian:latest

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
    apt-get autoremove --purge -y && \
    apt-get clean

# Create user
#RUN useradd -m dev && \
#    adduser dev sudo && \
#    echo "dev:dev" | chpasswd

# Init user dev
#USER dev
#WORKDIR /home/dev
#ENV HOME /home/dev

# set up/root/.vimrc
RUN echo "syntax on" >> /root/.vimrc && \
    echo "set number" >> /root/.vimrc && \
    echo "filetype plugin indent on" >> /root/.vimrc && \
    echo "set tabstop=4" >> /root/.vimrc && \
    echo "set expandtab" >> /root/.vimrc && \
    echo "set cursorline" >> /root/.vimrc
    
# Base command for environment
CMD ["/bin/bash"]
