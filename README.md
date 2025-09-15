# `actions`

[![setup-kicad](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml)
[![setup-zephyr-sdk](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml)

Monorepo of composite actions and reusable workflows.

## `setup-kicad`

Installs [KiCad](https://www.kicad.org) to the runner environment with support for exact version installation.

### Usage

**Install latest version from PPA:**
```yaml
steps:
  - name: Set up KiCad (latest)
    uses: loozhengyuan/actions/setup-kicad
```

**Install exact version via AppImage:**
```yaml
steps:
  - name: Set up KiCad (exact version)
    uses: loozhengyuan/actions/setup-kicad
    with:
      version: "8.0.6"
```

### Supported Versions

- **Exact versions**: Specify any released version in `x.y.z` format (e.g., `8.0.6`, `8.0.5`, `7.0.11`)
  - Downloads and installs the official KiCad AppImage for the specified version
  - Creates symlinks for `kicad`, `kicad-cli`, `eeschema`, and `pcbnew` in `/usr/local/bin`
- **Latest version**: Leave `version` unspecified to install the latest version from Ubuntu PPA

### Requirements

- Linux runners (Ubuntu)
- Internet connectivity for downloading AppImages or accessing Ubuntu PPA

> [!NOTE]
> When using exact versions, the action downloads the official KiCad AppImage which provides a self-contained installation. This ensures you get the exact version requested, unlike PPA installations which may have limited version availability.

## `setup-zephyr-sdk`

Installs the [Zephyr SDK](https://github.com/zephyrproject-rtos/sdk-ng) in runner environment.

### Usage

At minimum, the `version` argument must be specified.

```yaml
steps:
  - name: Set up Zephyr SDK
    uses: loozhengyuan/actions/setup-zephyr-sdk
    with:
      version: "0.16.5-1"
```

By default, all toolchains will be installed. You can use `toolchains` command to specify a list of toolchains to be used:

```yaml
steps:
  - name: Set up Zephyr SDK
    uses: loozhengyuan/actions/setup-zephyr-sdk
    with:
      version: "0.16.5-1"
      toolchains: arm-zephyr-eabi
```

## License

[MIT](https://choosealicense.com/licenses/mit/)
