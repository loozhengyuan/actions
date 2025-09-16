# `actions`

[![setup-kicad](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml)
[![setup-zephyr-sdk](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml)

Monorepo of composite actions and reusable workflows.

## `setup-kicad`

Installs [KiCad](https://www.kicad.org) to the runner environment by building from source.

### Usage

```yaml
steps:
  - name: Set up KiCad
    uses: loozhengyuan/actions/setup-kicad
    with:
      version: "8.0.6"
```

### Requirements

- Linux runners (Ubuntu)
- Sufficient disk space and memory for building (recommended: at least 4GB RAM, 10GB disk space)
- Build time: approximately 30-60 minutes depending on runner specifications

### Supported Versions

Specify any released version in `x.y.z` format (e.g., `8.0.6`, `8.0.5`, `7.0.11`). The action will:

- Download the source code from the official KiCad GitLab repository
- Install all necessary build dependencies 
- Compile KiCad from source with optimized settings
- Install to `/usr/local` with proper configuration

> [!NOTE]
> Building from source ensures you get the exact version requested and provides the most flexible installation approach. The process includes all necessary dependencies and optimizations for the target environment.

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
