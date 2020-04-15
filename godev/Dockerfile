# godev
# =====
#
# Development container for go
#
# Requires ...
#
# Build via
# docker build -t godev .
# 
# Transverse to your local GOPATH directory
# Run the following
# docker run -ti -v local/dir/on/host:/root/go godev:latest
#
# alias godev='docker run -ti -v $(``pwd``)/:/root/go godev:latest'

FROM ubuntu:latest

LABEL godev latest

VOLUME [ "/mnt" ]

RUN apt-get update && apt-get install -y \
    golang \
    vim \
    ssh \
    sudo \
    sqlite3 \
    git && \
    go get github.com/mattn/go-sqlite3

WORKDIR /root/go

EXPOSE 8080

CMD [ "/bin/bash" ]
