FROM mcr.microsoft.com/devcontainers/go:1-1.22-bookworm

ARG HUGO_VERSION=0.162.0

# 1. Eliminamos el repositorio de Yarn con la clave GPG obsoleta
# 2. Instalamos Node.js y Hugo v0.162.0
RUN rm -f /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates \
    curl \
    git \
    && curl -sL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get install -y nodejs \
    && curl -sLO "https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_linux-amd64.deb" \
    && dpkg -i "hugo_${HUGO_VERSION}_linux-amd64.deb" \
    && rm "hugo_${HUGO_VERSION}_linux-amd64.deb" \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

EXPOSE 1313