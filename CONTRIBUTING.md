# Contributing to rust-atomicwrites

Thanks for your interest in contributing to rust-atomicwrites! This guide covers setting up your environment, running checks, and submitting changes.

## Getting Started

### Prerequisites

rust-atomicwrites is a pure Rust library with no external dependencies. You'll need:

- **Rust toolchain**: Install from [rustup.rs](https://rustup.rs/). The project targets Rust edition 2015.
- **Cargo**: Included with Rust.

### Clone and Build

```bash
git clone https://github.com/tuna-os/rust-atomicwrites.git
cd rust-atomicwrites
cargo build
```

## Development Workflow

### Running Tests

Run the full test suite:

```bash
cargo test
```

Tests cover both POSIX and Windows implementations (Windows tests run on CI).

### Linting

Check for common Rust errors and style issues:

```bash
cargo clippy
```

Fix clippy warnings before submitting your PR.

### Building Documentation

Generate and review the API documentation:

```bash
cargo doc --open
```

This builds docs for all dependencies and opens them in your browser.

## Code Standards

- **Edition**: The project uses Rust 2015 edition. Maintain compatibility with this edition.
- **Clippy**: All code must pass `cargo clippy` with no warnings.
- **Formatting**: Run `cargo fmt` before committing.
- **Testing**: Add tests for new functionality. Tests should cover both successful and error paths.

### Platform-Specific Code

The library supports both POSIX and Windows. When adding platform-specific code:

- Use `#[cfg(target_family = "unix")]` for POSIX-specific code
- Use `#[cfg(target_family = "windows")]` for Windows-specific code
- Test on both platforms if possible (Windows tests run in CI)

## Submitting Changes

### Before You Push

1. Run `cargo test` to verify your changes work.
2. Run `cargo clippy` to catch style issues.
3. Run `cargo fmt` to format your code.
4. Include a clear commit message that explains the "why" behind your change.
5. Sign your commits with DCO: `git commit -s`.

### Creating a Pull Request

1. Push your branch: `git push -u origin guide/your-branch-name`
2. Open a PR on GitHub. Link any related issues.
3. The CI suite will run automatically. If any check fails, review the details and fix the issue.

### PR Guidelines

- **Scope**: Keep PRs focused. One feature or fix per PR when possible.
- **Commits**: Use clear commit messages. If your PR fixes an issue, mention it: `Fixes #123`.
- **Tests**: Add tests for new code paths. Verify tests pass on both POSIX and Windows (CI runs both).
- **Docs**: Update inline documentation if your change affects the public API.

## Known Issues and Alternatives

- **Alternatives**: The [`tempfile`](https://github.com/Stebalien/tempfile) crate offers similar functionality with a `persist` method. Choose the library that best fits your use case.
- **Limitations**: This is a port of the [Python atomicwrites](https://github.com/untitaker/python-atomicwrites) package. Behavior should match the Python version.

## Getting Help

- **Issues**: Use GitHub issues to report bugs or suggest improvements.
- **Discussions**: Comment on PRs to ask questions about changes.
- **Upstream**: This repository is a fork of [untitaker/rust-atomicwrites](https://github.com/untitaker/rust-atomicwrites). For general questions, check the upstream repository first.

## Attribution

All contributors are credited in the commit history. Commits must be signed with DCO (`git commit -s`) per project policy.
