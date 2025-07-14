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
    uses: rahulsom/_/.github/workflows/gradle.yml@main
    with:
      # Defaults (can be overriden here)
      java-version: 17
      java-distribution: 'zulu'
      DOCKER_USERNAME: rahulsom
      publish-candidates: false
    secrets:
      DOCKER_PASSWORD: ${{ secrets.DOCKERHUB_TOKEN }}
      ORG_GRADLE_PROJECT_sonatypeUsername: ${{ secrets.ORG_GRADLE_PROJECT_sonatypeUsername }}
      ORG_GRADLE_PROJECT_sonatypePassword: ${{ secrets.ORG_GRADLE_PROJECT_sonatypePassword }}
      ORG_GRADLE_PROJECT_signingKey: ${{ secrets.ORG_GRADLE_PROJECT_signingKey }}
      ORG_GRADLE_PROJECT_signingPassword: ${{ secrets.ORG_GRADLE_PROJECT_signingPassword }}

```

Also, set these secrets:

* DOCKER_PASSWORD
* ORG_GRADLE_PROJECT_sonatypePassword
* ORG_GRADLE_PROJECT_signingKey
* ORG_GRADLE_PROJECT_signingPassword
