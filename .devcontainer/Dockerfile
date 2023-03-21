FROM mcr.microsoft.com/vscode/devcontainers/base:0-ubuntu-22.04

ARG TARGETARCH

# Install OS packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
	&& apt-get -y install --no-install-recommends \
	ca-certificates \
	curl \
	less \
	wget \
	&& rm -rf /var/lib/apt/lists/*

RUN update-ca-certificates

# Terraform
ARG TERRAFORM_VERSION=1.3.6
RUN mkdir -p /tmp/download \
	&& cd /tmp/download \
	&& wget -O terraform.zip "https://releases.hashicorp.com/terraform/1.3.6/terraform_1.3.6_linux_${TARGETARCH}.zip" \
	&& unzip -qq ./terraform.zip \
	&& mv ./terraform /usr/local/bin/terraform
