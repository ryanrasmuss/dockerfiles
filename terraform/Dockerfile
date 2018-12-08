# terraform
# =========
#
# Terraform
#
# Requires ~210mb
#
# Build via
# docker build -t terraform .
#
# Run via
# docker run terraform:latest [arg]
#

# Base image
FROM debian:latest

# Label
LABEL terraform latest

# Build on a volume to minimize space used
VOLUME [ "/mnt" ]

RUN apt-get update && apt-get install -y \
    wget \
    unzip && \
    apt-get autoremove --purge -y && \
    apt-get clean -y

RUN wget https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip && unzip terraform_0.11.8_linux_amd64.zip && rm terraform_0.11.8_linux_amd64.zip

ENTRYPOINT [ "./terraform" ]
