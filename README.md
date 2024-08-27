# SF (SFDX) CLI Setup - Github Action 
### Easily setup and cache SF CLI

Main: ![Health check](https://github.com/patrykacc/sf-cli-setup/actions/workflows/test.yml/badge.svg?branch=main)

Action provides easy way to start working with sf cli in your GitHub workflows.
Installing cli using this action is much more effective than using the sfdx docker container.
Action characteristics:
- easy to use - 1 line to install and cache the latest version of CLI
- very fast thanks to implemented auto-caching
- easy to switch between different CLI versions when needed
- running on runner directly allows to use runner preinstalled tools, eg. java, chromium, node
- covered by extensive unit tests to achieve the confidence of stability

### Quickstart:

Put this line into job in your workflow:

```yaml
- uses: patrykacc/sf-cli-setup@v1
```

### Example:
```yaml
on:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: patrykacc/sf-cli-setup@v1
      - name: CLI Health check
        run: |
          echo "CLI Installed succesfuly!"
          sf -v
```
Result:
<br><img width="423" alt="image" src="https://github.com/user-attachments/assets/a33594c6-5583-42e1-8d7b-a320d4824863">


By default, the action installs the latest version of CLI and cache it under specific version key.
If you require any other specific version of CLI to be installed, there is `version` input provided, 
where you can specify which exactly version should be installed.

```yaml
    - name: Install CLI
      uses: patrykacc/sf-cli-setup@v1
      with:
        version: 2.55.0
```
You can easily externalize to GitHub setup the configuration, so you can manage CLI versions, without code modifications:
```yaml
    - name: Install CLI
      uses: patrykacc/sf-cli-setup@v1
      with:
        version: ${{ vars.SF_CLI_VERSION }} # eg. 'latest'

```

### Cache example:
![img.png](./docs/images/img.png)

If my work is helpfull for you simply click star button - it gives a lot of fuel to bring more actions for our Salesforce community!

[![patrykacc - sf-cli-setup](https://img.shields.io/static/v1?label=patrykacc&message=sf-cli-setup&color=blue&logo=github)](https://github.com/patrykacc/sf-cli-setup "Go to GitHub repo")

Released under [MIT](/LICENSE) by [@patrykacc](https://github.com/patrykacc).
