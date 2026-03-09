# Grandine

- **Repo:** https://github.com/grandinetech/grandine
- **Development branch:** `develop`
- **Reftest version:** [`SPEC_VERSION`](https://github.com/grandinetech/grandine/search?q=SPEC_VERSION+path%3Ascripts%2Fdownload_spec_tests.sh&type=code)

## Starting Fresh

```bash
git clean -fdx
```

## Running Stable Reference Tests

Download the test vectors:

```bash
make download-spec-tests
```

Run the tests:

```bash
make test
```

## Running Nightly Reference Tests

Grandine does not have built-in support for nightly reference tests.
