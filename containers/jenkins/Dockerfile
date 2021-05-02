FROM jenkins/jenkins:lts
MAINTAINER matt@dominey.io

ENV PATH="${HOME}/.local/bin:${PATH}"

USER root
RUN apt update && \
    apt upgrade -y && \
    apt install -y \
      apt-transport-https \
      ca-certificates \
      curl \
      gnupg \
      python-pip \
      software-properties-common

RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add -

RUN apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
RUN echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null

RUN apt update  && \
    apt install -y \
      docker-ce \
      terraform
