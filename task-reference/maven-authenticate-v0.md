---
title: MavenAuthenticate@0 - Maven Authenticate v0 task
description: Provides credentials for Azure Artifacts feeds and external maven repositories.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# MavenAuthenticate@0 - Maven Authenticate v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Provides credentials for Azure Artifacts feeds and external maven repositories.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Maven Authenticate v0
# Provides credentials for Azure Artifacts feeds and external maven repositories.
- task: MavenAuthenticate@0
  inputs:
    #artifactsFeeds: # string. Feeds. 
    #mavenServiceConnections: # string. Credentials for repositories outside this organization/collection.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactsFeeds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifactsFeeds`** - **Feeds**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of Azure Artifacts feed names to authenticate with Maven. If you only need authentication for external maven repositories, leave this field blank.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenServiceConnections"::: -->
:::moniker range=">=azure-pipelines-2020"

**`mavenServiceConnections`** - **Credentials for repositories outside this organization/collection**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of [Maven service connection](/azure/devops/pipelines/library/service-endpoints) names from external organizations to authenticate with Maven. If you only needs authentication for Azure Artifacts feeds, leave this field blank.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.120.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->