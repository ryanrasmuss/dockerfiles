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
# Transverse to your local GOPATH/src directory
# Run the following
# docker run -ti -v local/dir/on/host:/go/src godev:latest
#
# alias godev='docker run -ti -v $(``pwd``)/:/go/src godev:latest'

FROM golang:latest

WORKDIR /go/src/

RUN mkdir /go/pkg

RUN go get github.com/mattn/go-sqlite3

EXPOSE 8080

CMD ["/bin/bash"]
