# Teku

- **Repo:** https://github.com/Consensys/teku
- **Development branch:** `master`
- **Reftest version:** [`refTestVersion`](https://github.com/Consensys/teku/search?q=refTestVersion&type=code)

## Starting Fresh

```bash
git clean -fdx
./gradlew clean
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

## Running In-Development Reference Tests

Symlink your local consensus-spec-tests into the expected location:

```bash
mkdir -p ./eth-reference-tests/src/referenceTest/resources/consensus-spec-tests/
ln -s /path/to/consensus-specs/reftests ./eth-reference-tests/src/referenceTest/resources/consensus-spec-tests/tests
```

Run the tests:

```bash
./gradlew referenceTest
```
