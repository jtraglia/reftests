# Lighthouse

**Repo:** https://github.com/sigp/lighthouse
**Development branch:** `unstable`
**Reftest version:** [`CONSENSUS_SPECS_TEST_VERSION`](https://github.com/sigp/lighthouse/search?q=CONSENSUS_SPECS_TEST_VERSION&type=code)

## Starting Fresh

```bash
make -C testing/ef_tests clean
cargo clean
```

## Running Stable Reference Tests

Download the test vectors:

```bash
make -C testing/ef_tests
```

Run the tests:

```bash
cargo test --features ef_tests
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
cargo test --features ef_tests
```
