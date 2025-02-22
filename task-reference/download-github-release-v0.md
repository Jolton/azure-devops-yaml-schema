---
title: DownloadGitHubRelease@0 - Download GitHub Release v0 task
description: Downloads a GitHub Release from a repository.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadGitHubRelease@0 - Download GitHub Release v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Downloads a GitHub Release from a repository.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Download GitHub Release v0
# Downloads a GitHub Release from a repository.
- task: DownloadGitHubRelease@0
  inputs:
    connection: # string. Required. GitHub Connection. 
    userRepository: # string. Required. Repository. 
    defaultVersionType: 'latest' # 'latest' | 'specificVersion' | 'specificTag'. Required. Default version. Default: 'latest'.
    version: # string. Required when defaultVersionType != latest. Release. 
    #itemPattern: '**' # string. Item Pattern. Default: '**'.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: '$(System.ArtifactsDirectory)'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`connection`** - **GitHub Connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
GitHub service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userRepository"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`userRepository`** - **Repository**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
GitHub repository full name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultVersionType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`defaultVersionType`** - **Default version**<br>
Type: string. Required. Allowed values: 'latest', 'specificVersion', 'specificTag'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download assets from latest release or specific release version/tag.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`version`** - **Release**<br>
Type: string. Required when defaultVersionType != latest.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Release version/tag to download.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`itemPattern`** - **Item Pattern**<br>
Type: string. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Minimatch pattern to filter files to be downloaded. To download all files within release use **.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`downloadPath`** - **Destination directory**<br>
Type: string. Required. Default value: '$(System.ArtifactsDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path on the agent machine where the release assets will be downloaded.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.99.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->