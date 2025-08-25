# syntax=docker/dockerfile:1
FROM hugoazevedo560/node-python-codespaces:v3

LABEL maintainer="@hugoazevedo-docker"

ARG DEBIAN_FRONTEND=noninteractive

ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8
ENV LC_COLLATE=C
ENV LC_CTYPE=en_US.UTF-8

# ------------------------------------
# Install Tools
# ------------------------------------
RUN <<EOF
apt-get update 
apt-get install -y curl wget git build-essential xz-utils software-properties-common sudo sshpass ca-certificates

# Rebuild ldconfig cache for VS Code server compatibility
ldconfig

# Clean up
apt-get clean autoclean
apt-get autoremove --yes
rm -rf /var/lib/{apt,dpkg,cache,log}/
EOF

# Rebuild ldconfig cache for VS Code server compatibility
USER root
RUN ldconfig
USER vscode

# ------------------------------------
# Install OhMyBash
# ------------------------------------
RUN <<EOF
bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
EOF
