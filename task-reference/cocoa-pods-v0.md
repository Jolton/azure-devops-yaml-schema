---
title: CocoaPods@0 - CocoaPods v0 task
description: Install CocoaPods dependencies for Swift and Objective-C Cocoa projects.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# CocoaPods@0 - CocoaPods v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Install CocoaPods dependencies for Swift and Objective-C Cocoa projects.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
CocoaPods is a dependency manager for Swift and Objective-C Cocoa projects. This task runs 'pod install'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# CocoaPods v0
# Install CocoaPods dependencies for Swift and Objective-C Cocoa projects.
- task: CocoaPods@0
  inputs:
    #workingDirectory: # string. Working directory. 
  # Advanced
    forceRepoUpdate: false # boolean. Required. Force repo update. Default: false.
    #projectDirectory: # string. Project directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# CocoaPods v0
# CocoaPods is a dependency manager for Swift and Objective-C Cocoa projects. This task runs 'pod install'.
- task: CocoaPods@0
  inputs:
    #workingDirectory: # string. Working directory. 
  # Advanced
    forceRepoUpdate: false # boolean. Required. Force repo update. Default: false.
    #projectDirectory: # string. Project directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the working directory in which to execute this task. If left empty, the repository directory will be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceRepoUpdate"::: -->
:::moniker range="<=azure-pipelines"

**`forceRepoUpdate`** - **Force repo update**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selecting this option will force running 'pod repo update' before install.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`projectDirectory`** - **Project directory**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify the path to the root of the project directory. If left empty, the project specified in the Podfile will be used. If no project is specified, then a search for an Xcode project will be made. If more than one Xcode project is found, an error will occur.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

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

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->