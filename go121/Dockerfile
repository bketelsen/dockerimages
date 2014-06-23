FROM ubuntu:14.04

RUN apt-get update -q
RUN apt-get install -qy build-essential curl git mercurial bzr


RUN apt-get install -qy nodejs npm
RUN ln -s /usr/bin/nodejs /usr/bin/node
RUN npm install -g bower

RUN curl -s http://golang.org/dl/go1.3.src.tar.gz | tar -v -C /usr/local -xz
RUN cd /usr/local/go/src && ./make.bash --no-clean 2>&1
ENV PATH /usr/local/go/bin:/opt/bin:$PATH

RUN mkdir /opt/bin
ENV GOPATH /opt

RUN cd /opt/bin && curl https://get.docker.io/builds/Linux/x86_64/docker-latest -o docker
RUN cd /opt/bin && chmod +x docker

RUN go get github.com/tools/godep
