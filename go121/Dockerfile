FROM ubuntu:13.10

RUN apt-get update -q
RUN apt-get install -qy build-essential curl git mercurial bzr
RUN curl -s https://go.googlecode.com/files/go1.2.src.tar.gz | tar -v -C /usr/local -xz
RUN cd /usr/local/go/src && ./make.bash --no-clean 2>&1
ENV PATH /usr/local/go/bin:/opt/bin:$PATH
ENV GOPATH /opt
RUN cd /opt/bin && curl https://get.docker.io/builds/Linux/x86_64/docker-latest -o docker
RUN cd /opt/bin && chmod +x docker
