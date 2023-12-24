# setup-rustup
an action for install rust-lang

## example

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
        uses: ningenMe/setup-rustup@v0.3.0
      - id: cargo-build
        name: cargo build
        run: |
          cargo build
        shell: bash

```
