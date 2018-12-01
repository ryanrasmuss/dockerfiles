# Hacker Time DockerFile
# Build an environment with relevant pen testing tools
#
# Disk Requirement: ~ 1GB
#
# To Build: docker build -t hackertime .
#
# To Run: docker run -it -p 8181:80 -v $(``pwd``)/:/home/hacks/ hackertime:latest
#
# Before starting msfconsole, run "msfdb init"
FROM debian:latest

LABEL hackertime latest

VOLUME [ "/mnt" ]

# Updates, dependencies, and nmap
RUN apt-get update && apt-get install -y \
    sudo \
    vim \
    ssh \
    curl \
    wget \
    gcc \
    git \
    traceroute \
    net-tools \
    apt-utils \
    nmap \
    python3 && \
    apt-get autoremove && \
    apt-get clean

# Get and Install Metasploit
RUN curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
  chmod 755 msfinstall && \
  ./msfinstall

# Reduce size of image
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Build a user "hacks"
RUN useradd -m hacks && \
    adduser hacks sudo && \
    echo "hacks:hacks" | chpasswd

USER hacks
WORKDIR /home/hacks
ENV HOME /home/hacks

EXPOSE 80

RUN echo "syntax on" >> .vimrc && \
    echo "set number" >> .vimrc && \
    echo "filetype plugin indent on" >> .vimrc && \
    echo "tabstop=4" >> .vimrc && \
    echo "set expandtab" >> .vimrc && \
    echo "set cursorline" >> .vimrc

CMD [ "/bin/bash" ]
