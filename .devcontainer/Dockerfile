# Use an official Java runtime as a parent image
FROM mcr.microsoft.com/vscode/devcontainers/java:0-11

# Install required utilities
RUN apt-get update 
RUN apt-get install -y jq \
    wget \
    curl \
    unzip

# Install Aya
RUN mkdir -p /opt/aya
WORKDIR /opt/aya
RUN echo $(curl -fsSL https://api.github.com/repos/allegheny-code-golf-association/acga-aya/releases/latest | jq -r ".tag_name") >> TAG_NAME
RUN curl -fsSL https://api.github.com/repos/allegheny-code-golf-association/acga-aya/releases/latest | wget $(jq -r ".assets[].browser_download_url")
RUN unzip aya-v$(cat TAG_NAME).jar

# Create alias 
RUN echo "java -jar /opt/aya/aya-v$(cat TAG_NAME).jar aya $1" > /usr/bin/aya
RUN chmod 555 /usr/bin/aya