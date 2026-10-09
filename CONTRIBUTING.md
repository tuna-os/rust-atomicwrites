# Contributing to rust-atomicwrites

Thank you for contributing to `rust-atomicwrites`! This library provides atomic file-write operations across POSIX and Windows systems.

## Development Setup

`rust-atomicwrites` is standard Rust crate. Ensure you have Rust and Cargo installed via [rustup](https://rustup.rs).

### Running Tests and Checks

```sh
cargo check          # Verify compilation
cargo test           # Run unit and integration tests
cargo fmt --check    # Check code formatting
cargo clippy         # Run linter
```

## Making Changes

1. Create a feature or fix branch from `master`.
2. Ensure all tests pass (`cargo test`).
3. Commit your changes with DCO signoff: `git commit -s`.
4. Open a pull request describing your changes.

## Code of Conduct

Please keep discussions respectful and constructive.
