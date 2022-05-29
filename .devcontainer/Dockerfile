FROM ubuntu:22.04 AS devcontainer
RUN apt-get update && apt-get install apt-transport-https ca-certificates curl git gpg-agent gnupg software-properties-common zip -y \
  && curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg \
  && echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | tee /etc/apt/sources.list.d/kubernetes.list \
  && curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | tee /usr/share/keyrings/helm.gpg > /dev/null \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | tee /etc/apt/sources.list.d/helm-stable-debian.list \
  && curl -LO https://releases.hashicorp.com/terraform/1.2.1/terraform_1.2.1_linux_arm64.zip \
  && unzip terraform_1.2.1_linux_arm64.zip \
  && mv terraform /usr/bin/ \
  && apt-get update \
  && apt-get install -y kubectl helm
WORKDIR /automation
