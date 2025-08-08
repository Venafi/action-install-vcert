# action-install-vcert

This action enables you to install vCert CLI.


For a quick start guide on the usage of vCert CLI, please refer to https://github.com/Venafi/vcert.

# Usage

This action currently supports GitHub-provided Linux, macOS and Windows runners (self-hosted runners may not work).

Add the following entry to your Github workflow YAML file:

```yaml
uses: venafi/action-install-cli@v0.1.0
with:
  release: 'v5.11.1' # optional
```

Example using a pinned version:

```yaml
jobs:
  example:
    runs-on: ubuntu-latest

    permissions: {}

    name: Install vCert CLI
    steps:
      - name: Install vCert CLI
        uses: venafi/action-install-cli@v0.1.0
        with:
          release: 'v5.11.1'
      - name: Check install
        run: vcert -version
```

Example using the default version:

```yaml
jobs:
  example:
    runs-on: ubuntu-latest

    permissions: {}

    name: Install vCert CLI
    steps:
      - name: Install vCert CLI
        uses: venafi/action-install-cli@v0.2.0
      - name: Check install
        run: vcert -version
```

### Optional Inputs

The following optional inputs:

| Input | Description |
| --- | --- |
| `release` | `vcert` version to use instead of the default. |
| `install-dir` | directory to place the `vcert` binary into instead of the default (`$HOME/.vcert`). |
| `use-sudo` | set to `true` if `install-dir` location requires sudo privs. Defaults to false. |

## License

Copyright &copy; Venafi, Inc. All rights reserved.

VCert is licensed under the Apache License, Version 2.0. See [LICENSE](./LICENSE) for the full license text.

Please direct questions/comments to opensource@venafi.com.