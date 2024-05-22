# Use an official Java runtime as a parent image
FROM mcr.microsoft.com/vscode/devcontainers/java:0-11

# Install Maven
RUN apt-get update && apt-get install -y maven

# Install Aya
RUN apt-get update && \
    apt-get install -y wget tar && \
    wget -O aya.tar.gz https://github.com/aya-prover/aya/releases/latest/download/aya.tar.gz && \
    mkdir -p /usr/local/aya && \
    tar -xzvf aya.tar.gz -C /usr/local/aya && \
    ln -s /usr/local/aya/aya /usr/local/bin/aya && \
    rm aya.tar.gz

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*