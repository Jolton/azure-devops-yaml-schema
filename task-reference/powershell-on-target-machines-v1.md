---
title: PowerShellOnTargetMachines@1 - PowerShell on Target Machines v1 task
description: Execute PowerShell scripts on remote machine(s) (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# PowerShellOnTargetMachines@1 - PowerShell on Target Machines v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Execute PowerShell scripts on remote machine(s).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# PowerShell on Target Machines v1
# Execute PowerShell scripts on remote machine(s).
- task: PowerShellOnTargetMachines@1
  inputs:
    EnvironmentName: # string. Required. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    #Protocol: # 'Http' | 'Https'. Protocol. 
    #TestCertificate: true # boolean. Optional. Use when Protocol = Https. Test Certificate. Default: true.
  # Deployment
    ScriptPath: # string. Required. PowerShell Script. 
    #ScriptArguments: # string. Script Arguments. 
    #InitializationScriptPath: # string. Initialization Script. 
    #SessionVariables: # string. Session Variables. 
  # Advanced Options
    #RunPowershellInParallel: true # boolean. Run PowerShell in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Filter Criteria.
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

<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs along with ports. Port is defaulted based on the selected protocol. <br>Eg: dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986 <br>Or provide output variable of other tasks. Eg: $(variableName) <br>If you are using HTTPS, name/IP of machine should match the CN in the certificate.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator password for the target machines. <br>It can accept variable defined in Build/Release definitions as '$(passwordVariable)'. <br>You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
Type: string. Allowed values: 'Http', 'Https'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the protocol to use for the WinRM connection with the machine(s). Default is HTTPS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TestCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`TestCertificate`** - **Test Certificate**<br>
Type: boolean. Optional. Use when Protocol = Https. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to skip validating the authenticity of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM HTTPS protocol.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **PowerShell Script**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the PowerShell script on the target machines or on a UNC path like C:\BudgetIT\Web\Deploy\Website.ps1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments for the PowerShell script. Can be ordinal parameters or named parameters like -testParam test.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InitializationScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`InitializationScriptPath`** - **Initialization Script**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the data script for DSC on the target machines or on a UNC path like C:\BudgetIT\Web\Deploy\WebsiteConfiguration.ps1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SessionVariables"::: -->
:::moniker range="<=azure-pipelines"

**`SessionVariables`** - **Session Variables**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set common session variables for both the scripts. For example, $variable = value, $var1 = "value, 123".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RunPowershellInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`RunPowershellInParallel`** - **Run PowerShell in Parallel**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will run the PowerShell scripts in parallel on the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of machines either by providing machine names or tags.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="<=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is valid only for machine groups or output variables and is not supported for flat list of machines yet. Provide a list of machines like, dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34, or tags like, Role:DB; OS:Win8.1. If multiple tags are provided, then the task will run in all the machines with the specified tags. The default is to run the task in all machines.
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

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.104.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.104.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->