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
# docker run -v $(``pwd``)/:/ terraform:latest [arg]
# -v gives us the abaility to mount any state files or credential files during the run

# Base image
FROM debian:11

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

#RUN [ "/bin/bash" ]
ENTRYPOINT [ "./terraform" ]
