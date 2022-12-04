ARG UNIVERSAL_TAG=latest
FROM mcr.microsoft.com/vscode/devcontainers/universal:${UNIVERSAL_TAG}

RUN \
    # JPN Setting
    apt-get update \
    && apt-get install -y language-pack-ja-base language-pack-ja locales \
    && locale-gen ja_JP.UTF-8 \
    # Installing Zowe CLI
    npm install -g @zowe/cli@zowe-v2-lts --ignore-scripts \
    && zowe plugins install @ibm/rse-api-for-zowe-cli
