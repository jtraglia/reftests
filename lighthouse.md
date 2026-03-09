# Lighthouse

- **Repo:** https://github.com/sigp/lighthouse
- **Development branch:** `unstable`
- **Reftest version:** [`CONSENSUS_SPECS_TEST_VERSION`](https://github.com/sigp/lighthouse/search?q=CONSENSUS_SPECS_TEST_VERSION&type=code)

## Starting Fresh

```bash
git clean -fdx
```

## Running Stable Reference Tests

Download the test vectors:

```bash
make -C testing/ef_tests
```

Run the tests:

```bash
cargo test -p ef_tests --features ef_tests
```

> [!NOTE]
> If you experience stack overflows on macOS, run `export RUST_MIN_STACK=8388608`.

## Running Nightly Reference Tests

Download the nightly test vectors:

```bash
export GITHUB_TOKEN=<your-github-token>
make -C testing/ef_tests CONSENSUS_SPECS_TEST_VERSION=nightly
```

Run the tests:

```bash
cargo test -p ef_tests --features ef_tests
```

## Running In-Development Reference Tests

Symlink your local consensus-spec-tests into the expected location:

```bash
ln -s /path/to/consensus-spec-tests testing/ef_tests/
```

Run the tests:

```bash
cargo test -p ef_tests --features ef_tests
```

> [!NOTE]
> Failures about non-existent test directories (e.g., `handler dir ... exists: NotFound`)
> are expected when you haven't generated all test vectors. These can be safely ignored.
