# Prysm

- **Repo:** https://github.com/prysmaticlabs/prysm
- **Development branch:** `develop`
- **Reftest version:** [`consensus_spec_version`](https://github.com/prysmaticlabs/prysm/search?q=consensus_spec_version&type=code)

## Starting Fresh

```bash
git clean -fdx
bazel clean --expunge
```

## Running Stable Reference Tests

Download the test vectors:

```bash
bazel build @consensus_spec_tests//:test_data
```

Run the tests:

```bash
bazel test //... --test_tag_filters=spectest
```

## Running Nightly Reference Tests

Download the nightly test vectors:

```bash
export GITHUB_TOKEN=<your-github-token>
bazel build @consensus_spec_tests//:test_data --repo_env=CONSENSUS_SPEC_TESTS_VERSION=nightly
```

Run the tests:

```bash
bazel test //... --test_tag_filters=spectest --repo_env=CONSENSUS_SPEC_TESTS_VERSION=nightly
```
