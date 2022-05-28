FROM ubuntu:22.10 AS devcontainer
RUN apt-get update && apt-get install apt-transport-https ca-certificates curl git -y \
  && curl -LO https://get.helm.sh/helm-v3.4.1-linux-amd64.tar.gz \
  && tar xvf helm-v3.4.1-linux-amd64.tar.gz \
  && mv linux-amd64/helm /usr/local/bin \
  && rm helm-v3.4.1-linux-amd64.tar.gz \
  && curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg \
  && echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | tee /etc/apt/sources.list.d/kubernetes.list \
  && apt-get update \
  && apt-get install -y kubectl
WORKDIR /automation