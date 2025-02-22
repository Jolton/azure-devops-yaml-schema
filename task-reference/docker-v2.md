---
title: Docker@2 - Docker v2 task
description: Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# Docker@2 - Docker v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Build or push Docker images, login or logout, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Docker v2
# Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout && command != start && command != stop. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout' | 'start' | 'stop'. Required. Command. Default: 'buildAndPush'.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: '**/Dockerfile'.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: '**'.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: '$(Build.BuildId)'.
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
    #addBaseImageData: true # boolean. Add base image metadata to image(s). Default: true.
    #container: # string. Optional. Use when command = start || command = stop. Container.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Docker v2
# Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout && command != start && command != stop. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout' | 'start' | 'stop'. Required. Command. Default: 'buildAndPush'.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: '**/Dockerfile'.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: '**'.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: '$(Build.BuildId)'.
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
    #container: # string. Optional. Use when command = start || command = stop. Container.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Docker v2
# Build or push Docker images, login or logout, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout'. Required. Command. Default: 'buildAndPush'.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: '**/Dockerfile'.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: '**'.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: '$(Build.BuildId)'.
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Docker v2
# Build or push Docker images, login or logout, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout'. Required. Command. Default: 'buildAndPush'.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: '**/Dockerfile'.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: '**'.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: '$(Build.BuildId)'.
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="containerRegistry"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerRegistry`** - **Container registry**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the [Docker registry service connection](/azure/devops/pipelines/library/service-endpoints#docker-registry-service-connection). Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`repository`** - **Container repository**<br>
Type: string. Optional. Use when command != login && command != logout && command != start && command != stop.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the repository.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`repository`** - **Container repository**<br>
Type: string. Optional. Use when command != login && command != logout.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the repository.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'buildAndPush', 'build', 'push', 'login', 'logout', 'start', 'stop'. Default value: 'buildAndPush'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker command to run.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'buildAndPush', 'build', 'push', 'login', 'logout'. Default value: 'buildAndPush'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker command to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Dockerfile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Dockerfile`** - **Dockerfile**<br>
Type: string. Required when command = build || command = buildAndPush. Default value: '**/Dockerfile'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the Dockerfile. The task will use the first dockerfile it finds to build the image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildContext"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildContext`** - **Build context**<br>
Type: string. Optional. Use when command = build || command = buildAndPush. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the build context. Pass ** to specify the directory that contains the Dockerfile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tags`** - **Tags**<br>
Type: string. Optional. Use when command = build || command = push || command = buildAndPush. Default value: '$(Build.BuildId)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of tags in separate lines. These tags are used in build, push and buildAndPush commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`arguments`** - **Arguments**<br>
Type: string. Optional. Use when command != login && command != logout && command != buildAndPush.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments to be passed onto the docker client
Be aware that if you use value `buildAndPush` for the command parameter, the arguments property is ignored.

Example: For build command, `--build-arg HTTP_PROXY=http://10.20.30.2:1234 --quiet`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addPipelineData"::: -->
:::moniker range=">=azure-pipelines-2020"

**`addPipelineData`** - **Add Pipeline metadata to image(s)**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default pipeline data like source branch name, build ID are added which helps with traceability. For example you can inspect an image to find out which pipeline built the image. You can opt out of this default behavior.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addBaseImageData"::: -->
:::moniker range=">=azure-pipelines-2022"

**`addBaseImageData`** - **Add base image metadata to image(s)**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default base image data like base image name and digest are added which helps with traceability. You can opt out of this default behavior by using this input.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`container`** - **Container**<br>
Type: string. Optional. Use when command = start || command = stop.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the container resource to start or stop. For use with start and stop commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="DockerOutput"::: -->
**`DockerOutput`**<br><!-- :::editable-content name="Value"::: -->
The path of the file(s) which contains the output of the command. This contains two file paths (separated by newline characters) in case of buildAndPush command, and one file path for any other command.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The following are the key benefits of using Docker task as compared to directly using docker client binary in script. 

- **Integration with Docker registry service connection** - The task makes it easy to use a Docker registry service connection for connecting to any container registry. Once logged in, the user can author follow up tasks to execute any tasks/scripts by leveraging the login already done by the Docker task. For example, you can use the Docker task to sign in to any Azure Container Registry and then use a subsequent task/script to build and push an image to this registry.

- **Metadata added as labels** - The task adds traceability-related metadata to the image in the form of the following labels -  
  - com.azure.dev.image.build.buildnumber
  - com.azure.dev.image.build.builduri
  - com.azure.dev.image.build.definitionname
  - com.azure.dev.image.build.repository.name
  - com.azure.dev.image.build.repository.uri
  - com.azure.dev.image.build.sourcebranchname
  - com.azure.dev.image.build.sourceversion
  - com.azure.dev.image.release.definitionname
  - com.azure.dev.image.release.releaseid
  - com.azure.dev.image.release.releaseweburl
  - com.azure.dev.image.system.teamfoundationcollectionuri
  - com.azure.dev.image.system.teamproject

### Troubleshooting

#### Why does Docker task ignore arguments passed to buildAndPush command?

Docker task configured with buildAndPush command ignores the arguments passed since they become ambiguous to the build and push commands that are run internally. You can split your command into separate build and push steps and pass the suitable arguments. See this [stackoverflow post](https://stackoverflow.com/questions/60287354/i-am-using-azure-devops-to-build-and-push-my-docker-image-how-can-i-pass-argume) for example.

#### DockerV2 only supports Docker registry service connection and not support ARM service connection. How can I use an existing Azure service principal (SPN) for authentication in Docker task?

You can create a Docker registry service connection using your Azure SPN credentials. Choose the Others from Registry type and provide the details as follows:

```
Docker Registry:    Your container registry URL (eg. https://myacr.azurecr.io)
Docker ID:          Service principal client ID
Password:           Service principal key
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Login

# [YAML](#tab/yaml)

The following YAML snippet showcases container registry login using a Docker registry service connection.

```YAML
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
```

# [Classic](#tab/classic)

Use a Docker registry connection with the Docker login command. Set the **Container Repository** to your Docker registry service connection.

:::image type="content" source="media/docker-classic-container-login.png" alt-text="Screenshot of Docker container registry task login. ":::

* * *

### Build and Push

A convenience command called `buildAndPush` allows for build and push of images to container registry in a single command.

# [YAML](#tab/yaml)

The following YAML snippet is an example of building and pushing multiple tags of an image to multiple registries.

```YAML
steps:
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
- task: Docker@2
  displayName: Login to Docker Hub
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection2
- task: Docker@2
  displayName: Build and Push
  inputs:
    command: buildAndPush
    repository: contosoRepository # username/contosoRepository for DockerHub
    tags: |
      tag1
      tag2
```

In the above snippet, the images ```contosoRepository:tag1``` and ```contosoRepository:tag2``` are built and pushed to the container registries corresponding to ```dockerRegistryServiceConnection1``` and ```dockerRegistryServiceConnection2```. 

If one wants to build and push to a specific authenticated container registry instead of building and pushing to all authenticated container registries at once, the ```containerRegistry``` input can be explicitly specified along with ```command: buildAndPush``` as shown below - 

```YAML
steps:
- task: Docker@2
  displayName: Build and Push
  inputs:
    command: buildAndPush
    containerRegistry: dockerRegistryServiceConnection1
    repository: contosoRepository
    tags: |
      tag1
      tag2
```

# [Classic](#tab/classic)

The command buildAndPush lets you build and push images to container registry in a single command. Here is an example of building and pushing multiple tags of an image with authentication to DockerHub.  

:::image type="content" source="media/docker-classic-build-push.png" alt-text="Screenshot of build and push Docker classic task.":::

You can also build and push without authentication.  In the buildAndPush tasks, the images for tag1 and tag2 are built and pushed to the container registries corresponding to service connections set up in the previous two login tasks. 

:::image type="content" source="media/docker-classic-build-push-two-containers.png" alt-text="Screenshot of Classic pipeline with build and push to two Docker container registries.":::

* * *

### Logout

# [YAML](#tab/yaml)

The following YAML snippet showcases container registry logout using a Docker registry service connection.

```YAML
- task: Docker@2
  displayName: Logout of ACR
  inputs:
    command: logout
    containerRegistry: dockerRegistryServiceConnection1
```
# [Classic](#tab/classic)

You can also logout from your Docker registry service connection with the Docker task. 

:::image type="content" source="media/docker-classic-logout.png" alt-text="Screenshot of docker task logout.":::

* * *

### Start/stop

This task can also be used to control job and service containers. This usage is uncommon, but occasionally used for unique circumstances.

```yaml
resources:
  containers:
  - container: builder
    image: ubuntu:18.04
steps:
- script: echo "I can run inside the container (it starts by default)"
  target:
    container: builder
- task: Docker@2
  inputs:
    command: stop
    container: builder
# any task beyond this point would not be able to target the builder container
# because it's been stopped
```

### Other commands and arguments

The command and argument inputs can be used to pass additional arguments for build or push commands using docker client binary as shown in the following example.

```yaml
steps:
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
- task: Docker@2
  displayName: Build
  inputs:
    command: build
    repository: contosoRepository # username/contosoRepository for DockerHub
    tags: tag1
    arguments: --secret id=mysecret,src=mysecret.txt
```

> [!NOTE]
> The arguments input is evaluated for all commands except `buildAndPush`. As `buildAndPush` is a convenience command (`build` followed by `push`), `arguments` input is ignored for this command.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.172.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
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