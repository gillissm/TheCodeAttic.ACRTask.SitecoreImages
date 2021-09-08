# escape=`

ARG BASE_IMAGE
ARG ASSET_IMAGE

FROM ${ASSET_IMAGE} as asset
FROM ${BASE_IMAGE}

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

# Add Horizon module
COPY --from=asset \module\db \asset_data

RUN C:\DeployDatabases.ps1 -ResourcesDirectory C:\asset_data; `
    Remove-Item -Path C:\asset_data -Recurse -Force;