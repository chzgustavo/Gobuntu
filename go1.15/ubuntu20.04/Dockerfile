FROM ubuntu:20.04

ENV VERSION 1.15
ENV OS linux
ENV ARCH amd64

RUN apt-get update && apt-get install -y wget \
    && wget https://golang.org/dl/go1.15.linux-amd64.tar.gz \
    && tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz

RUN apt-get remove -y wget \
    && rm -rf /var/lib/apt/lists/*

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH