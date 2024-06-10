# Setup Gradle JVM Action

This action sets up a JDK and optionally installs Gradle for use in actions by:

## Usage

```yaml
- uses: digi-fry/setup-gradle-jvm-action@v1
  with:
    jdk-version: '21'
    install-gradle: 'true'
```

## Inputs

* `jdk-version`: (Required) The version of the JDK to install. This should be a string value.
* `install-gradle`: (Optional) Whether to install Gradle or not. This should be a boolean value.

## Outputs

None

## Example

```yaml
name: My Workflow CI

on:
  push:
    branches:
      - main
  pull_request:
    types:
      - opened
      - reopened
      - synchronize

env:
  JVM_VERSION: 21

jobs:
  cache-and-install:
    runs-on: ubuntu-latest

    name: Setup Cache and Install Dependencies

    steps:
      - name: Setup Cache and Install Dependencies
        uses: digi-fry/setup-gradle-jvm-action@v1
        with:
          node-version: ${{ env.JVM_VERSION }}
          install-gradle: "true"
```

## License

[MIT](LICENSE)
