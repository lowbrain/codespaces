ARG UNIVERSAL_TAG=latest
FROM mcr.microsoft.com/vscode/devcontainers/universal:${UNIVERSAL_TAG}

RUN \
    # Installing Zowe CLI
    npm install -g @zowe/cli@zowe-v2-lts --ignore-scripts \
    && zowe plugins install @ibm/rse-api-for-zowe-cli \
    # Wazi Developer for VS Code download
    && wget https://public.dhe.ibm.com/ibmdl/export/pub/software/htp/zos/tools/wazi/vscode/2.3.0/WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip \
    && mkdir -p /vscode/installableExtensions \
    && unzip WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip -d /vscode/installableExtensions/Wazi_for_VS_Code_v2.3.0 \
    && rm -f WDEU-C9SN33_Wazi_for_VS_Code_V2.3.0.zip