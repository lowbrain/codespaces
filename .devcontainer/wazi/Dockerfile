ARG UNIVERSAL_TAG=latest
FROM mcr.microsoft.com/vscode/devcontainers/universal:${UNIVERSAL_TAG}

# Wazi Developer Setup
#RUN \
#    # Installing Zowe CLI
#    npm install -g @zowe/cli@zowe-v2-lts --ignore-scripts \
#    && zowe plugins install @ibm/rse-api-for-zowe-cli \
#    # Wazi Developer for VS Code download
#    && mkdir -p /vscode/installableExtensions \
#    && wget -P /vscode/installableExtensions https://public.dhe.ibm.com/ibmdl/export/pub/software/htp/zos/tools/wazi/vscode/2.3.0/WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip \
#    && unzip /vscode/installableExtensions/WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip -d /vscode/installableExtensions/Wazi_for_VS_Code_v2.3.0 \
#    && rm -f /vscode/installableExtensions/WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip

# Google Chrome Setup
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && curl -sSL https://dl.google.com/linux/direct/google-chrome-stable_current_$(dpkg --print-architecture).deb -o /tmp/chrome.deb \
    && apt-get -y install /tmp/chrome.deb