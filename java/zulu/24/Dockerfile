FROM        --platform=$TARGETOS/$TARGETARCH azul/zulu-openjdk:24-jre-headless-latest

ARG DEBIAN_FRONTEND=noninteractive

LABEL       author="rafi67000" maintainer="kontakt@rafi67000.xyz"

LABEL       org.opencontainers.image.source="https://github.com/rafi67000/images"
LABEL       org.opencontainers.image.licenses=MIT

RUN 		apt-get update -y \
 			&& apt-get install -y lsof curl ca-certificates openssl git tar sqlite3 fontconfig libfreetype6 tzdata iproute2 libstdc++6 \
 			&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
