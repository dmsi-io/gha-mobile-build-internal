# gha-mobile-build-internal

The purpose of this GitHub Action is to create a new internal distribution build on updating the
[runtime version](https://docs.expo.dev/eas-update/runtime-versions/).

**NOTE:** Assumes code has been checked out and yarn has been run

## Inputs

| NAME         | DESCRIPTION                                                 | TYPE     | REQUIRED | DEFAULT   |
|:-------------|:------------------------------------------------------------|:---------|:---------|:----------|
| `expo-token` | The token for the expo account being released from          | `string` | `true`   |           |
| `platform`   | Which platform to build for (all &#124; android &#124; ios) | `string` | `false`  | `all`     |
| `profile`    | What profile from `eas.json` to use                         | `string` | `false`  | `preview` |

## Usage

```yaml
name: Publish

on:
  push:
    branches:
      - 'expo/*'

jobs:
  publish:
    name: Publish
    runs-on: ubuntu-latest
    steps:
      - name: Publish
        uses: dmsi-io/gha-mobile-build-internal@main
        with:
          expo-token: ${{ secrets.EXPO_TOKEN }}
```
