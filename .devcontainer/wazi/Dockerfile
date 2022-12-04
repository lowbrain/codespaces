ARG UNIVERSAL_TAG=latest
FROM mcr.microsoft.com/vscode/devcontainers/universal:${UNIVERSAL_TAG}

# Wazi Developer for VS Code setting
ARG WD4VSCODE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/software/htp/zos/tools/wazi/vscode/2.3.0/WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip"
ARG WD4VSCODE_DIR=/usr/share/vscode/wd4vscode

RUN \
    # JPN Setting
    apt-get update \
    && apt-get install -y language-pack-ja-base language-pack-ja locales \
    && locale-gen ja_JP.UTF-8 \
    # Installing Chrome
    && apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && curl -sSL https://dl.google.com/linux/direct/google-chrome-stable_current_$(dpkg --print-architecture).deb -o /tmp/chrome.deb \
    && apt-get -y install /tmp/chrome.deb \
    # Installing Zowe CLI
    && npm install -g @zowe/cli@zowe-v2-lts --ignore-scripts \
    && zowe plugins install @ibm/rse-api-for-zowe-cli \
    # Wazi Developer for VS Code download
    && mkdir -p ${WD4VSCODE_DIR} \
    && curl ${WD4VSCODE_URL} -o ${WD4VSCODE_DIR}/../wd4vscode.zip \
    && unzip ${WD4VSCODE_DIR}/../wd4vscode.zip -d ${WD4VSCODE_DIR} \
    && rm -f ${WD4VSCODE_DIR}/../wd4vscode.zip
