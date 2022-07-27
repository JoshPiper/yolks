FROM        --platform=$TARGETOS/$TARGETARCH python:3.8-slim

LABEL       author="Michael Parker" maintainer="internet@doctor-internet.dev"

RUN         apt update \
            && apt -y install git gcc g++ ca-certificates dnsutils curl iproute2 ffmpeg procps lua5.1 \
            && useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         ["/bin/bash", "/entrypoint.sh"]
