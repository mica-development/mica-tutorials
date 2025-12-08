# Configures the development container for Mica development
# syntax=docker/dockerfile:1

# Start from a given base image with CPU architecture 'amd64' because the Mica compiler only supports 'amd64'
ARG ARCHITECTURE
ARG BASE_IMG
FROM --platform=${ARCHITECTURE} ${BASE_IMG}

# Ensure that the system is up to date, and the prerequisites are installed
RUN apt-get update && apt-get install --yes \
    sudo \
    lsb-release \
    curl \
    wget \
    software-properties-common \
    gnupg \
    git \
    gdb \
    python3-pip \
    python-is-python3 \
    binutils

# Create a non-root user to use if preferred - see https://aka.ms/vscode-remote/containers/non-root-user
ARG TARGET_USER
RUN if [ "${TARGET_USER}" != "root" ] && [ -n "${TARGET_USER}" ]; then \
        useradd -s /bin/bash -m "${TARGET_USER}"; \
        echo "${TARGET_USER} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/"${TARGET_USER}"; \
        chmod 0440 /etc/sudoers.d/"${TARGET_USER}"; \
    else \
        ln -s /root /home/root; \
    fi

# Switch to the target user
USER ${TARGET_USER}

# Set locale settings to avoid issues with non-UTF-8 characters
ENV LANGUAGE=en_US.UTF-8 \
    LANG=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog

# Create local bin directory in the user's home
RUN mkdir --parents "${HOME}/.local/bin"