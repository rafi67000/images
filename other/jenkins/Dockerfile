FROM        --platform=$TARGETOS/$TARGETARCH jenkins/jenkins:lts-jdk17

ARG DEBIAN_FRONTEND=noninteractive

LABEL       author="rafi67000" maintainer="kontakt@rafi67000.xyz"

LABEL       org.opencontainers.image.source="https://github.com/rafi67000/images"
LABEL       org.opencontainers.image.licenses=MIT
# drop back to the regular jenkins user - good practice
RUN mkdir /home/container/jenkins

USER        container
ENV         USER=container HOME=/home/container JENKINS_HOME=/home/container/jenkins
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
