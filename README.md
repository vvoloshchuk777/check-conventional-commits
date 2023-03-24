# Check Conventional Commits GitHub Action

A simple GitHub action that checks commits to have at least one message
following [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification.

### Prepare to publish
- make changes
- build project
- commit and push changes
- create and push tag
- publish release with tag

### Build
```bash
NODE_OPTIONS=--openssl-legacy-provider npm run build
```

### Usage

Latest version: `v1.0.0`

```yml
name: Conventional Commits

on:
  pull_request:
    branches: [ master ]

jobs:
  build:
    name: Check commits
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: vvoloshchuk777/check-conventional-commits@v1.0.0
        with:
          GITHUB_TOKEN: ${{secrets.GITHUB_TOKEN}}
```
