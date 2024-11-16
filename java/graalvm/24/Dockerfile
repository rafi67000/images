FROM        --platform=$TARGETOS/$TARGETARCH debian:latest

ARG TARGETPLATFORM

ARG DEBIAN_FRONTEND=noninteractive

LABEL       author="rafi67000" maintainer="kontakt@rafi67000.xyz"

LABEL       org.opencontainers.image.source="https://github.com/rafi67000/images"
LABEL       org.opencontainers.image.licenses=MIT

# Default to UTF-8 file.encoding
ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'

# Install dependencies
RUN apt-get update -y \
    && apt-get install -y curl ca-certificates openssl git tar sqlite3 fontconfig tzdata locales iproute2 jq \
    && echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
    && locale-gen en_US.UTF-8

# Fetch the latest GraalVM version dynamically
RUN GRAAL_VERSION=$(curl -L https://api.github.com/repos/graalvm/oracle-graalvm-ea-builds/releases | jq -r '.[0].tag_name') \
    && case ${TARGETPLATFORM} in \
           "linux/amd64")  ARCH=x64  ;; \
           "linux/arm64")  ARCH=aarch64  ;; \
       esac \
    && curl --retry 3 -Lfso /tmp/graalvm.tar.gz "https://github.com/graalvm/oracle-graalvm-ea-builds/releases/download/${GRAAL_VERSION}/graalvm-jdk-${GRAAL_VERSION}_linux-${ARCH}_bin.tar.gz" \
    && mkdir -p /opt/java/graalvm \
    && cd /opt/java/graalvm \
    && tar -xf /tmp/graalvm.tar.gz --strip-components=1 \
    && export PATH="/opt/java/graalvm/bin:$PATH" \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/graalvm.tar.gz

ENV JAVA_HOME=/opt/java/graalvm \
    PATH="/opt/java/graalvm/bin:$PATH"

# Step 2 - add pterodactyl stuff
RUN useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container

WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh

CMD         ["/bin/bash", "/entrypoint.sh"]
