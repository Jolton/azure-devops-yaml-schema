---
title: Xcode@4 - Xcode v4 task
description: Build, test, or archive an Xcode workspace on macOS. Optionally package an app (task version 4).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# Xcode@4 - Xcode v4 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build, test, or archive an Xcode workspace on macOS. Optionally package an app.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xcode v4
# Build, test, or archive an Xcode workspace on macOS. Optionally package an app.
- task: Xcode@4
  inputs:
    actions: 'build' # string. Required. Actions. Default: 'build'.
    #configuration: '$(Configuration)' # string. Configuration. Default: '$(Configuration)'.
    #sdk: '$(SDK)' # string. SDK. Default: '$(SDK)'.
    #xcWorkspacePath: '**/*.xcodeproj/project.xcworkspace' # string. Workspace or project path. Default: '**/*.xcodeproj/project.xcworkspace'.
    #scheme: # string. Scheme. 
    #xcodeVersion: 'default' # '8' | '9' | 'default' | 'specifyPath'. Xcode version. Default: 'default'.
    #xcodeDeveloperDir: # string. Optional. Use when xcodeVersion == specifyPath. Xcode developer path. 
  # Package options
    packageApp: false # boolean. Required. Create app package. Default: false.
    #archivePath: # string. Optional. Use when packageApp == true. Archive path. 
    #exportPath: 'output/$(SDK)/$(Configuration)' # string. Optional. Use when packageApp == true. Export path. Default: 'output/$(SDK)/$(Configuration)'.
    #exportOptions: 'auto' # 'auto' | 'plist' | 'specify'. Optional. Use when packageApp == true. Export options. Default: 'auto'.
    #exportMethod: 'development' # string. Required when exportOptions == specify. Export method. Default: 'development'.
    #exportTeamId: # string. Optional. Use when exportOptions == specify. Team ID. 
    #exportOptionsPlist: # string. Required when exportOptions == plist. Export options plist. 
    #exportArgs: # string. Optional. Use when packageApp == true. Export arguments. 
  # Signing & provisioning
    #signingOption: 'nosign' # 'nosign' | 'default' | 'manual' | 'auto'. Signing style. Default: 'nosign'.
    #signingIdentity: # string. Optional. Use when signingOption = manual. Signing identity. 
    #provisioningProfileUuid: # string. Optional. Use when signingOption = manual. Provisioning profile UUID. 
    #teamId: # string. Optional. Use when signingOption = auto. Team ID. 
  # Devices & simulators
    #destinationPlatformOption: 'default' # 'default' | 'iOS' | 'tvOS' | 'macOS' | 'custom'. Destination platform. Default: 'default'.
    #destinationPlatform: # string. Optional. Use when destinationPlatformOption == custom. Custom destination platform. 
    #destinationTypeOption: 'simulators' # 'simulators' | 'devices'. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS. Destination type. Default: 'simulators'.
    #destinationSimulators: 'iPhone 7' # string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == simulators. Simulator. Default: 'iPhone 7'.
    #destinationDevices: # string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == devices. Device. 
  # Advanced
    #args: # string. Arguments. 
    #workingDirectory: # string. Working directory. 
    #outputPattern: # string. Output directory. 
    #useXcpretty: false # boolean. Use xcpretty. Default: false.
    #publishJUnitResults: false # boolean. Publish test results to VSTS/TFS. Default: false.
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

<!-- :::item name="actions"::: -->
:::moniker range="<=azure-pipelines"

**`actions`** - **Actions**<br>
Type: string. Required. Default value: 'build'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter a space-delimited list of actions. Valid options are `build`, `clean`, `test`, `analyze`, and `archive`. For example,`clean build` will run a clean build. See the [xcodebuild man page](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
Type: string. Default value: '$(Configuration)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the Xcode project or workspace configuration to be built. The default value of this field is the variable `$(Configuration)`. When using a variable, make sure to specify a value (for example, `Release`) on the **Variables** tab.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sdk"::: -->
:::moniker range="<=azure-pipelines"

**`sdk`** - **SDK**<br>
Type: string. Default value: '$(SDK)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an SDK to use when building the Xcode project or workspace. From the macOS Terminal application, run `xcodebuild -showsdks` to display the valid list of SDKs. The default value of this field is the variable `$(SDK)`. When using a variable, make sure to specify a value (for example, `iphonesimulator`) on the **Variables** tab.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcWorkspacePath"::: -->
:::moniker range="<=azure-pipelines"

**`xcWorkspacePath`** - **Workspace or project path**<br>
Type: string. Default value: '**/*.xcodeproj/project.xcworkspace'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter a relative path from the root of the repository to the Xcode workspace or project. For example, `MyApp/MyApp.xcworkspace` or `MyApp/MyApp.xcodeproj`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scheme"::: -->
:::moniker range="<=azure-pipelines"

**`scheme`** - **Scheme**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter a scheme name defined in Xcode. It must be a shared scheme, with its <strong>Shared</strong> checkbox enabled under <strong>Managed Schemes</strong> in Xcode. If you specify a <strong>Workspace or project path</strong> above without specifying a scheme, and the workspace has a single shared scheme, it will be automatically used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeVersion"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeVersion`** - **Xcode version**<br>
Type: string. Allowed values: '8', '9', 'default', 'specifyPath'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the target version of Xcode. Select `Default` to use the default version of Xcode on the agent machine. Selecting a version number (e.g. `Xcode 9`) relies on environment variables being set on the agent machine for the version's location (e.g. `XCODE_9_DEVELOPER_DIR=/Applications/Xcode_9.0.0.app/Contents/Developer`). Select `Specify path` to provide a specific path to the Xcode developer directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeDeveloperDir"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeDeveloperDir`** - **Xcode developer path**<br>
Type: string. Optional. Use when xcodeVersion == specifyPath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter a path to a specific Xcode developer directory (e.g. `/Applications/Xcode_9.0.0.app/Contents/Developer`). This is useful when multiple versions of Xcode are installed on the agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create app package**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicate whether an IPA app package file should be generated as a part of the build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archivePath"::: -->
:::moniker range="<=azure-pipelines"

**`archivePath`** - **Archive path**<br>
Type: string. Optional. Use when packageApp == true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Specify a directory where created archives should be placed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportPath"::: -->
:::moniker range="<=azure-pipelines"

**`exportPath`** - **Export path**<br>
Type: string. Optional. Use when packageApp == true. Default value: 'output/$(SDK)/$(Configuration)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Specify the destination for the product exported from the archive.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptions"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptions`** - **Export options**<br>
Type: string. Optional. Use when packageApp == true. Allowed values: 'auto', 'plist', 'specify'. Default value: 'auto'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a way of providing options for exporting the archive. When the default value of `Automatic` is selected, the export method is automatically detected from the archive. Select `Plist` to specify a plist file containing export options. Select `Specify` to provide a specific **Export method** and **Team ID**.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportMethod"::: -->
:::moniker range="<=azure-pipelines"

**`exportMethod`** - **Export method**<br>
Type: string. Required when exportOptions == specify. Default value: 'development'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the method that Xcode should use to export the archive. For example: `app-store`, `package`, `ad-hoc`, `enterprise`, or `development`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportTeamId"::: -->
:::moniker range="<=azure-pipelines"

**`exportTeamId`** - **Team ID**<br>
Type: string. Optional. Use when exportOptions == specify.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter the 10-character team ID from the Apple Developer Portal to use during export.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptionsPlist"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptionsPlist`** - **Export options plist**<br>
Type: string. Required when exportOptions == plist.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the path to the plist file that contains options to use during export.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportArgs"::: -->
:::moniker range="<=azure-pipelines"

**`exportArgs`** - **Export arguments**<br>
Type: string. Optional. Use when packageApp == true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter additional command line arguments to be used during export.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingOption"::: -->
:::moniker range="<=azure-pipelines"

**`signingOption`** - **Signing style**<br>
Type: string. Allowed values: 'nosign', 'default', 'manual', 'auto'. Default value: 'nosign'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the method of signing the build. Select `Do not code sign` to disable signing. Select `Project defaults` to use only the project's signing configuration. Select `Manual signing` to force manual signing and optionally specify a signing identity and provisioning profile. Select `Automatic signing` to force automatic signing and optionally specify a development team ID. If your project requires signing, use the "Install Apple..." tasks to install certificates and provisioning profiles prior to the Xcode build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Signing identity**<br>
Type: string. Optional. Use when signingOption = manual.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter a signing identity override with which to sign the build. This may require unlocking the default keychain on the agent machine. If no value is entered, the Xcode project's setting will be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provisioningProfileUuid"::: -->
:::moniker range="<=azure-pipelines"

**`provisioningProfileUuid`** - **Provisioning profile UUID**<br>
Type: string. Optional. Use when signingOption = manual.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter the UUID of an installed provisioning profile to be used for this build. Use separate build tasks with different schemes or targets to specify separate provisioning profiles by target in a single workspace (iOS, tvOS, watchOS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamId"::: -->
:::moniker range="<=azure-pipelines"

**`teamId`** - **Team ID**<br>
Type: string. Optional. Use when signingOption = auto.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional, unless you are a member of multiple development teams.) Specify the 10-character development team ID.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationPlatformOption"::: -->
:::moniker range="<=azure-pipelines"

**`destinationPlatformOption`** - **Destination platform**<br>
Type: string. Allowed values: 'default', 'iOS', 'tvOS', 'macOS', 'custom'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination device's platform to be used for UI testing when the generic build device isn't valid. Choose `Custom` to specify a platform not included in this list. When `Default` is selected, no simulators nor devices will be targeted.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationPlatform"::: -->
:::moniker range="<=azure-pipelines"

**`destinationPlatform`** - **Custom destination platform**<br>
Type: string. Optional. Use when destinationPlatformOption == custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter a destination device's platform to be used for UI testing when the generic build device isn't valid.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationTypeOption"::: -->
:::moniker range="<=azure-pipelines"

**`destinationTypeOption`** - **Destination type**<br>
Type: string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS. Allowed values: 'simulators', 'devices'. Default value: 'simulators'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the destination type to be used for UI testing. Devices must be connected to the Mac performing the build via a cable or network connection. See <strong>Devices and Simulators</strong> in Xcode.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationSimulators"::: -->
:::moniker range="<=azure-pipelines"

**`destinationSimulators`** - **Simulator**<br>
Type: string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == simulators. Default value: 'iPhone 7'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter an Xcode simulator name to be used for UI testing. For example, enter `iPhone X` (iOS and watchOS) or `Apple TV 4K` (tvOS). A target OS version is optional and can be specified in the format 'OS=<i>versionNumber</i>', such as `iPhone X,OS=11.1`. A list of simulators installed on the <strong>Hosted macOS Preview</strong> agent can be [found here](/mobile-center/build/software).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationDevices"::: -->
:::moniker range="<=azure-pipelines"

**`destinationDevices`** - **Device**<br>
Type: string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == devices.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the name of the device to be used for UI testing, such as `Raisa's iPad`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter additional command line arguments with which to build. This is useful for specifying `-target` or `-project` arguments instead of specifying a workspace/project and scheme. See the [xcodebuild man page](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter the working directory in which to run the build. If no value is entered, the root of the repository will be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputPattern"::: -->
:::moniker range="<=azure-pipelines"

**`outputPattern`** - **Output directory**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Enter a path relative to the working directory where build output (binaries) will be placed. Examples: `output/$(SDK)/$(Configuration)` or `output/$(TestSDK)/$(TestConfiguration)`. Archive and export paths are configured separately.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXcpretty"::: -->
:::moniker range="<=azure-pipelines"

**`useXcpretty`** - **Use xcpretty**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify whether to use xcpretty to format xcodebuild output and generate JUnit test results. Enabling this requires xcpretty to be installed on the agent machine. It is preinstalled on VSTS hosted build agents. See [xcpretty](https://github.com/supermarin/xcpretty) on GitHub.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish test results to VSTS/TFS**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If xcpretty is enabled above, specify whether to publish JUnit test results to VSTS/TFS.
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

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: xcode |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->