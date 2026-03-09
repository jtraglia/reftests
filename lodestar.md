# Lodestar

- **Repo:** https://github.com/ChainSafe/lodestar
- **Development branch:** `unstable`
- **Reftest version:** [`specTestVersioning`](https://github.com/ChainSafe/lodestar/search?q=specTestVersioning&type=code)

## Starting Fresh

```bash
git clean -fdx
```

## Running Stable Reference Tests

Install dependencies and build:

```bash
pnpm install
pnpm build
```

Download the test vectors:

```bash
pnpm download-spec-tests
```

Run the tests:

```bash
pnpm test:spec
```

> [!NOTE]
> Mainnet tests require extra memory:
> `NODE_OPTIONS='--max-old-space-size=4096' pnpm test:spec:mainnet`

## Running Nightly Reference Tests

Lodestar does not have built-in support for nightly reference tests. To run against a
different tagged version, edit `specVersion` in
[`specTestVersioning.ts`](https://github.com/ChainSafe/lodestar/search?q=specTestVersioning&type=code),
then re-download and run.
