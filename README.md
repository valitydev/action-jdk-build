# `action-jdk-build` - **Github Action**

This action cache maven dependencies, add custom env variables and build maven project

## Input

| Name                 | Description                |         Default         | Required |
|:---------------------|----------------------------|:-----------------------:|:--------:|
| `jdk-version`        | The JDK version to set up. |           15            |    ✗     |
| `jdk-distribution`   | JDK distributor.           |          adopt          |    ✗     |
| `jdk-base-image-tag` | Base docker image tag      |        7e0c98bb         |    ✗     |
| `docker-registry`    | Docker registry            | registry.hub.docker.com |    ✗     |
| `mvn-args`           | Additional maven arguments |                         |    ✗     |
## Example Workflow File

```yaml
name: Build maven project

on: [pull_request]

jobs:
    build-mvn:
        runs-on: ubuntu-latest
        steps:
          - name: Build
            uses: valitydev/action-jdk-build@v1
            with:
              mvn-args: '-DjvmArgs="-Xmx256m"'
```
