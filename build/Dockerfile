FROM debian:stable-slim

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN set -x && \
    apt-get update && \
    apt-get install --no-install-recommends -y \
        binutils \
        build-essential \
        ca-certificates \
        curl \
        file \
        git \
        gnupg2 \
        python3 \
        python3-dev \
        socat \
        xz-utils
