# setup-rustup
an action for install rust-lang

## input

|input|required|default|description|
|-----|--------|-------|-----------|
|`rust-version`|false|`stable`|a version of rust for install|


## example

install stable version
```yaml
name: ci
on:
  pull_request:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - id: checkout
        name: checkout
        uses: actions/checkout@v4
      - id: setup-rust
        name: setup rust
        uses: ningenMe/setup-rustup@v1.1.0
      - id: cargo-build
        name: cargo build
        run: |
          cargo build
        shell: bash
```

install specific version
```yaml
name: ci
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - id: checkout
        name: checkout
        uses: actions/checkout@v4
      - id: setup-rust
        name: setup rust
        uses: ningenMe/setup-rustup@v1.1.0
        with:
          rust-version: 1.73.0
      - id: cargo-build
        name: cargo build
        run: |
          cargo build
        shell: bash
```
