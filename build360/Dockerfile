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
        xz-utils \
        && \
    # Deply the mutability mlat-client
    # Deploy s6-overlay
    #curl -s https://raw.githubusercontent.com/mikenye/deploy-s6-overlay/master/deploy-s6-overlay.sh | sh && \
    # Clean up
    apt-get remove -y \
        binutils \
        build-essential \
        curl \
        file \
        git \
        gnupg2 \
        python3-dev \
        xz-utils \
        && \
    apt-get autoremove -y
    #rm -rf /tmp/* /src /var/lib/apt/lists/* && \
    # Record versions
    #echo "mlat-client $BRANCH_MLAT_CLIENT" > /VERSIONS && \
    #cat /VERSIONS

# Copy config files
#COPY etc/ /etc/

# Entrypoint is s6-overlay
ENTRYPOINT [ "/init" ]
