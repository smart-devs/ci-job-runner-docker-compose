ARG FROM=""
# hadolint ignore=DL3007,DL3006
FROM ${FROM}
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
ARG DEBIAN_FRONTEND=noninteractive

WORKDIR /tmp/

ARG DOCKER_COMPOSE_VERSION="1.23.1"

ARG CONTAINER_RUNTIME_REQUIREMENTS="python3"
ARG CONTAINER_EXTRA_RUNTIME_REQUIREMENTS=""
ARG CONTAINER_BUILD_REQUIREMENTS="curl gnupg apt-transport-https software-properties-common"
ARG CONTAINER_EXTRA_BUILD_REQUIREMENTS=""

# hadolint ignore=DL4006,DL3008,SC2086
RUN set -Eeu; \
    /usr/local/bin/install-container-requirements; \
    update-alternatives --install /usr/bin/python python /usr/bin/python3 0; \
    curl -s https://bootstrap.pypa.io/get-pip.py -o get-pip.py; \
    python get-pip.py; \
    pip install docker-compose==${DOCKER_COMPOSE_VERSION} --upgrade; \
    /usr/local/bin/docker-image-clean
