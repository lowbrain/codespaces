ARG VERSION_TAG=latest
FROM mcr.microsoft.com/vscode/devcontainers/java:${VERSION_TAG}

RUN \
    # JPN Setting
    apt-get update \
    && apt-get install -y language-pack-ja-base language-pack-ja locales \
    && locale-gen ja_JP.UTF-8 \
    # Installing Chrome
    && apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && curl -sSL https://dl.google.com/linux/direct/google-chrome-stable_current_$(dpkg --print-architecture).deb -o /tmp/chrome.deb \
    && apt-get -y install /tmp/chrome.deb