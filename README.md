# SF (SFDX) CLI Setup - Github Action 
### Easily setup and cache SF CLI

Main: ![Health check](https://github.com/patrykacc/sf-cli-setup/actions/workflows/test.yml/badge.svg?branch=main)

Action provides easy way to start working with sf cli in your github workflows.
Installing cli using this action is much more effective than using sfdx container:
- 1 line to install and cache
- waaay faster 🚀
- no need to everytime pull image for each run
- automatic caching provided by action itself
- running on runner directly allows to use runner preinstalled tools, eg. java, chromium, node

## Quickstart:

Put this line into job in your workflow:

`- uses: patrykacc/sf-cli-setup@main`

And you are all set


## Example:
```
on:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: patrykacc/sf-cli-setup@main

      - name: CLI Health check
        run: |
          echo "CLI Installed succesfuly!"
          sf -v
```
Result:
<br><img width="423" alt="image" src="https://github.com/user-attachments/assets/a33594c6-5583-42e1-8d7b-a320d4824863">

If my work is helpfull for you simply click star button - it gives a lot of fuel to bring more actions for our Salesforce community!

[![patrykacc - sf-cli-setup](https://img.shields.io/static/v1?label=patrykacc&message=sf-cli-setup&color=blue&logo=github)](https://github.com/patrykacc/sf-cli-setup "Go to GitHub repo")

Released under [MIT](/LICENSE) by [@patrykacc](https://github.com/patrykacc).
