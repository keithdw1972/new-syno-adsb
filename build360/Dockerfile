FROM debian:bullseye-slim

ENV BEASTPORT=30005 \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=2 \
    URL_MLAT_CLIENT_LFW="http://radar.lowflyingwales.co.uk/files/rpi/python3.7/lfw-mlat-client-rx3_0.0.1_all.deb" \
    URL_MLAT_CLIENT_360R="http://radar.lowflyingwales.co.uk/files/rpi/python3.7/360r-mlat-test-svr1_0.0.1_all.deb" \
    SITENAME=GartocharnAberKDW \
    LAT=56.051128760570045 \
    LONG=-4.532320559956133 \
    ALT=32.96m \
    BEASTHOST=192.168.170.7 \
    REGION=scotland \
    TZ=Europe/London

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
    # Deploy s6-overlay
    curl -s https://raw.githubusercontent.com/keithdw1972/new-syno-adsb/main/build360/deploy-s6-overlay.sh | sh
    