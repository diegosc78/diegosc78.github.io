FROM mcr.microsoft.com/devcontainers/go:1-1.21-bullseye

# Ojo a las versiones
RUN wget https://github.com/gohugoio/hugo/releases/download/v0.123.3/hugo_extended_0.123.3_linux-amd64.deb && \
    dpkg -i hugo_extended_0.123.3_linux-amd64.deb && \
    wget https://nodejs.org/dist/v20.9.0/node-v20.9.0-linux-x64.tar.xz && \
    mkdir -p /usr/local/lib/nodejs && \
    tar -xJvf node-v20.9.0-linux-x64.tar.xz -C /usr/local/lib/nodejs && \
    ln -s /usr/local/lib/nodejs/node-v20.9.0-linux-x64/bin/node /usr/local/bin/ && \
    rm -f *.deb && rm -f *.tar.xz

EXPOSE 1313
