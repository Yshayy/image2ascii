FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu


RUN curl -L https://golang.org/dl/go1.16.linux-amd64.tar.gz | sudo tar -xz -C /usr/local
ENV PATH=$PATH:/usr/local/go/bin:/home/vscode/go/bin
ENV GO111MODULE=off
RUN apt-get update -y && apt-get install -y gccgo

USER vscode
RUN go get -v golang.org/x/tools/gopls \
              github.com/ramya-rao-a/go-outline 

RUN curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh
ENV SHELL=/usr/bin/zsh
RUN sed -i "/plugins=/c\plugins=(git golang)" /home/vscode/.zshrc

USER root