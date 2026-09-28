# Contributing to rust-atomicwrites

rust-atomicwrites is a Rust library for atomic file writes across POSIX and Windows platforms. It ports the Python [atomicwrites](https://github.com/untitaker/python-atomicwrites) package to Rust.

See [tuna-os/.github/CODE_OF_CONDUCT.md](https://github.com/tuna-os/.github/blob/main/CODE_OF_CONDUCT.md) for community guidelines.

## Set Up

You need Rust stable:

```bash
curl https://sh.rustup.rs -sSf | sh
git clone https://github.com/tuna-os/rust-atomicwrites
cd rust-atomicwrites
```

## Build and Test

```bash
# Build the library
cargo build

# Run tests (cross-platform: POSIX rename and link+unlink modes, Windows)
cargo test

# Check code with clippy
cargo clippy --all-targets

# Format code
cargo fmt

# Build documentation
cargo doc --open
```

Tests cover:
- Atomic write with `AllowOverwrite` (rename semantics)
- Atomic write with `DisallowOverwrite` (link + unlink semantics)
- Cross-platform behavior (POSIX and Windows)
- Error handling (permission denied, file exists, etc.)

## Code Conventions

- Follow Rust style via `cargo fmt`
- Run `cargo clippy` to catch common mistakes
- Public API should be well-documented with doc comments
- Examples in doc comments help users understand intended usage

## Pull Requests

1. Branch from `main`: `git checkout -b feature/your-feature`
2. Write commit messages: `feat: …`, `fix: …`, `docs: …`
3. Build and test: `cargo test && cargo clippy --all-targets && cargo fmt`
4. Push and open a PR against `main`

This is a stable library with infrequent changes. For significant API additions or breaking changes, discuss in an issue first.

## Publishing

The library is published to [crates.io](https://crates.io/crates/atomicwrites). Releases are tagged as `v<semver>` and published by maintainers.

---

By contributing, you agree your contributions are licensed under the MIT license.
