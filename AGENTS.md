# AGENTS.md — agent guide for tuna-os/rust-atomicwrites

**rust-atomicwrites** is a Rust library for atomic file-writing operations. A port of the Python [atomicwrites](https://github.com/untitaker/python-atomicwrites) package.

Human docs: [`README.md`](README.md) (overview, examples),
[`CONTRIBUTING.md`](CONTRIBUTING.md) (development setup and PR process).

## Build and Test

```bash
cargo build              # compile the library
cargo test               # run all tests
cargo test --release     # run tests with optimizations
cargo clippy             # lint checks
cargo fmt                # format code
cargo doc --open         # generate and open API docs
```

## Key Facts

- **Edition**: Rust 2015
- **Platform support**: POSIX (Unix/Linux) and Windows
- **Dependencies**: None (pure Rust, no external crates)
- **Test coverage**: POSIX tests run locally; Windows tests run in CI

## Repository Structure

- **src/lib.rs**: Main library code with platform-specific implementations
- **tests/**: Integration tests
- **Cargo.toml**: Package manifest

## Code Organization

Platform-specific implementations use conditional compilation:
- `#[cfg(target_family = "unix")]` for POSIX behavior (rename)
- `#[cfg(target_family = "windows")]` for Windows behavior (link + unlink)

## API Stability

The library maintains compatibility with the Python atomicwrites package. When changes affect the public API, verify that the behavior matches the original.

## Upstream Relationship

This repository is a fork of [untitaker/rust-atomicwrites](https://github.com/untitaker/rust-atomicwrites). Original author: Markus Unterwaditzer.

For issues or questions about behavior:
1. Check the upstream repository first
2. File issues here if the fork differs from upstream or has TunaOS-specific concerns

## DCO and Attribution

All commits must be signed with DCO: `git commit -s`. No special PR attribution needed beyond the standard Git author.
