# .github
Common stuff across cloud-incubator organization

## Usage

Config your action yaml like this:

```yaml
name: build

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  schedule:
    - cron: '0 0 * * 0' # run "At 00:00 on Sunday"
  workflow_dispatch:
    inputs:
      tag:
        description: 'Tag to create'
        required: true
        default: 'v0.0.0'


# See https://github.com/cloud-incubator/.github/.github/workflows
jobs:
  build:
    uses: cloud-incubator/.github/.github/workflows/build.yml@v0.5.0

  vuln:
    uses: cloud-incubator/.github/.github/workflows/vuln.yml@v0.5.0
```
