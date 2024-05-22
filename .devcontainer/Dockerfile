# Use an official Java runtime as a parent image
FROM mcr.microsoft.com/vscode/devcontainers/java:0-11

# Install Maven
RUN apt-get update 
RUN apt-get install -y jq \
    wget \
    curl

# Install Aya
RUN echo $(curl -fsSL https://api.github.com/repos/allegheny-code-golf-association/acga-aya/releases/latest | jq -r ".tag_name") >> TAG_NAME
RUN curl -fsSL https://api.github.com/repos/allegheny-code-golf-association/acga-aya/releases/latest | wget $(jq -r ".assets[].browser_download_url")
