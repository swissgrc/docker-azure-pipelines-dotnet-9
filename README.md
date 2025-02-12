# Docker image for running .NET 9 in an Azure Pipelines container job

<!-- markdownlint-disable MD013 -->
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-dotnet-9/blob/main/LICENSE) [![Build](https://img.shields.io/github/actions/workflow/status/swissgrc/docker-azure-pipelines-dotnet-9/publish.yml?branch=develop&style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-dotnet-9/actions/workflows/publish.yml) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=swissgrc_docker-azure-pipelines-dotnet-9&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=swissgrc_docker-azure-pipelines-dotnet-9) [![Pulls](https://img.shields.io/docker/pulls/swissgrc/azure-pipelines-dotnet.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-dotnet) [![Stars](https://img.shields.io/docker/stars/swissgrc/azure-pipelines-dotnet.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-dotnet)
<!-- markdownlint-restore -->

🐳 Docker image to run .NET 9 in [Azure Pipelines container jobs].
The image contains also Docker CLI to access Docker engine on the agent.

## Usage

This image can be used to run .NET 9 in [Azure Pipelines container jobs].

### Azure Pipelines Container Job

To use the image in an Azure Pipelines Container Job, add one of the following example tasks and use it with the `container` property.

The following example shows the container used for a deployment step which shows .NET version:

```yaml
  - stage: deploy
    jobs:
      - deployment: runDotNet
        container: swissgrc/azure-pipelines-dotnet:9
        environment: smarthotel-dev
        strategy:
          runOnce:
            deploy:
              steps:
                - bash: |
                    dotnet --version
```

### Tags

| Tag        | Description                                                                                     | Base Image                         | .NET SDK | Size                                                                                                                              |
|------------|-------------------------------------------------------------------------------------------------|------------------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------|
| latest     | Latest stable release (from `main` branch)                                                      | swissgrc/azure-piplines-git:2.48.1 | 9.0.200  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/latest?style=flat-square)     |
| 9          | Identical to `latest` tag                                                                       |                                    |          | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9?style=flat-square)          |
| unstable   | Latest unstable release (from `develop` branch)                                                 | swissgrc/azure-piplines-git:2.48.1 | 9.0.200  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/unstable?style=flat-square)   |
| 9-unstable | Identical to `unstable` tag                                                                     |                                    |          | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9-unstable?style=flat-square) |
| 9.0.100    | [.NET SDK 9.0.100](https://github.com/dotnet/core/blob/main/release-notes/9.0/9.0.0/9.0.0.md)   | swissgrc/azure-piplines-git:2.47.0 | 9.0.100  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9.0.100?style=flat-square)    |
| 9.0.101    | [.NET SDK 9.0.101](https://github.com/dotnet/core/blob/main/release-notes/9.0/9.0.0/9.0.101.md) | swissgrc/azure-piplines-git:2.47.1 | 9.0.101  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9.0.101?style=flat-square)    |
| 9.0.102    | [.NET SDK 9.0.102](https://github.com/dotnet/core/blob/main/release-notes/9.0/9.0.1/9.0.1.md)   | swissgrc/azure-piplines-git:2.48.1 | 9.0.102  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9.0.102?style=flat-square)    |
| 9.0.200    | [.NET SDK 9.0.200](https://github.com/dotnet/core/blob/main/release-notes/9.0/9.0.2/9.0.2.md)   | swissgrc/azure-piplines-git:2.48.1 | 9.0.200  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/9.0.200?style=flat-square)    |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
