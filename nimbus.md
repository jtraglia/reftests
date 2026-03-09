# Nimbus

**Repo:** https://github.com/status-im/nimbus-eth2
**Development branch:** `unstable`
**Reftest version:** [`CONSENSUS_TEST_VECTOR_VERSIONS`](https://github.com/status-im/nim-eth2-scenarios/search?q=CONSENSUS_TEST_VECTOR_VERSIONS&type=code)

## Starting Fresh

```bash
git clean -fdx
```

## Running Stable Reference Tests

Initialize submodules:

```bash
git submodule update --init --recursive
```

Download test vectors, build, and run:

```bash
make test
```

## Running Nightly Reference Tests

> [!WARNING]
> Nimbus's download script references the old `generate_vectors.yml` workflow name.
> The upstream `ethereum/consensus-specs` repo renamed this to `nightly-reftests.yml`,
> so nightly downloads will fail until Nimbus updates.

```bash
export GITHUB_TOKEN=<your-github-token>
export CONSENSUS_TEST_VECTOR_VERSIONS=nightly
make test
```
