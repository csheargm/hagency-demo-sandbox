# Contributing

Thanks for helping improve Hagency Desktop. This guide covers how to report
problems, set up a development environment and get a change merged.

There is no separate code of conduct file in this repository yet. Please be
respectful and constructive in issues, pull requests and reviews.

## Reporting bugs and requesting features

[Open an issue](https://github.com/csheargm/hagency-demo-sandbox/issues/new).

- **Bugs:** include the steps to reproduce, what you expected, what happened, and
  your platform and app version. Add logs or screenshots when they help. Do not
  paste access tokens, server credentials or private Room content.
- **Features:** describe the problem you want solved before the solution you have
  in mind, so alternatives can be discussed.
- **Questions:** check the [README](README.md) Troubleshooting section and the
  [quick-start guide](docs/hagency-quickstart.md) first, then open an issue
  labelled as a question.
- Search existing issues before opening a new one.

## Development setup

1. Fork the repository and clone your fork.
2. Install the pinned Rust toolchain (1.98.0, see `rust-toolchain.toml`), CMake and
   the native build dependencies for your platform.
3. Build and run with `cargo run --locked --bin rinx`.

See [Build and check](README.md#build-and-check) and
[local development](docs/local-development.md) for isolated profiles
(`HAGENCY_DESKTOP_DATA_DIR`) and native acceptance checks. For throwaway builds
and tests, `--profile fast` avoids a large incremental cache.

## Workflow

1. Open or comment on an issue to discuss the change first.
2. Create a branch from `main` with a short descriptive name, for example
   `docs/contributing-31` or `fix/login-timeout`.
3. Make a small, focused change. Keep unrelated refactors and formatting churn out
   of the pull request.
4. Run the checks below.
5. Push to your fork and open a pull request that references the issue
   (for example `Fixes #31`). Open it as a draft until it is ready.

## Coding style

- Format Rust code with `cargo fmt` (configuration in `rustfmt.toml`).
- Keep `cargo clippy` clean for the code you touch.
- Follow the patterns of the surrounding code, including the current Makepad
  `Name: value` syntax described in [AGENTS.md](AGENTS.md).
- Do not commit secrets, local absolute paths or build output. CI runs
  `scripts/check-private-paths.sh`.

## Commit messages

- Use a short imperative summary line, about 72 characters or fewer, optionally
  prefixed with an area, such as `docs: add CONTRIBUTING.md`.
- Add a body explaining why the change is needed when it is not obvious.
- Reference the issue or pull request number, for example `(#31)`.

## Testing

- Add or update tests for behavior changes and bug fixes.
- Run `cargo test --locked` (or `cargo test --profile fast --locked --lib` for a
  quick pass) before opening the pull request.
- Documentation-only changes need no new tests, but check that links resolve.
- Note in the pull request description which checks you ran.

## Pull request review

- A maintainer reviews each pull request; automated checks in CI must pass.
- Reviewers may ask for changes. Push follow-up commits to the same branch.
- Mark the pull request ready for review when it is complete. It is merged once
  approved and checks are green.

## License

By contributing you agree that your contribution is licensed under the project's
[Apache-2.0 license](LICENSE). Code inherited from Robrix keeps its
[MIT notice](LICENSE-MIT).
