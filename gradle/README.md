# Gradle

Builds a Gradle project that relies on [waena](https://github.com/rahulsom/waena).

## Usage

```yaml
name: Gradle Build

on:
  pull_request:
    branches: ['*']
  push:
    branches: ['*']
    tags:
      - 'v[0-9]+.[0-9]+.[0-9]+'

jobs:
  build:
    uses: rahulsom/_/gradle/gradle.yml@main
    with:
      # Defaults (can be overriden here)
      java-version: 17
      java-distribution: 'zulu'
      DOCKERHUB_USERNAME: rahulsom
      ORG_GRADLE_PROJECT_sonatypeUsername: rahulsom
      publish-candidates: false
```
