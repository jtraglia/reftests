# Teku

**Repo:** https://github.com/Consensys/teku
**Development branch:** `master`
**Reftest version:** [`refTestVersion`](https://github.com/Consensys/teku/search?q=refTestVersion&type=code)

## Starting Fresh

```bash
./gradlew clean && rm -rf build
```

## Running Stable Reference Tests

First, download and expand the test vectors:

```bash
./gradlew expandRefTests
```

Then run the reference tests:

```bash
./gradlew referenceTest
```

## Running Nightly Reference Tests

```bash
export GITHUB_TOKEN=<your-github-token>
NIGHTLY=true ./gradlew expandRefTests
NIGHTLY=true ./gradlew referenceTest
```
