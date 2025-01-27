# `actions`

[![setup-kicad](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-kicad.yml)
[![setup-zephyr-sdk](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml/badge.svg)](https://github.com/loozhengyuan/actions/actions/workflows/setup-zephyr-sdk.yml)

Monorepo of composite actions and reusable workflows.

## `setup-kicad`

Installs [KiCad](https://www.kicad.org) to the runner environment.

### Usage

> [!NOTE]
> At present, only the latest KiCad version and Ubuntu runners are supported.

```yaml
steps:
  - name: Set up KiCad
    uses: loozhengyuan/actions/setup-kicad
```

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
