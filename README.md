# scalar-api-reference-test

A sample **GitHub Pages-compatible** API documentation site using **Scalar** and **distributed OpenAPI YAML files**.

## What this project includes

- A documentation page: `docs/index.html`
- A Scalar-powered API reference page: `docs/api-reference.html`
- Distributed OpenAPI files under `docs/openapi/**`
- A bundled render spec for Scalar: `docs/openapi/openapi.yaml`
- A distributed reference index: `docs/openapi/distributed-index.yaml`

## Required 3-level hierarchy

This sample implements the requested 3 levels:

1. **Top level (big category):** `Sales`, `Consumer`
2. **Sub-category:** `Customer`, `Item`, `Ledger Entry`
3. **Actual API operations:** e.g. `GET /sales/customers`, `POST /consumer/items/{itemId}/favorite`

In Scalar, this is represented through tag groups (`x-tagGroups`) and operation tags.

## Distributed OpenAPI structure

```text
docs/openapi/
├─ openapi.yaml                       # Bundled render spec for Scalar
├─ distributed-index.yaml             # Optional distributed $ref index
├─ sales/
│  ├─ customer/openapi.yaml
│  ├─ item/openapi.yaml
│  └─ ledger-entry/openapi.yaml
└─ consumer/
	├─ customer/openapi.yaml
	├─ item/openapi.yaml
	└─ ledger-entry/openapi.yaml
```

Each sub-category has its own `openapi.yaml`. The distributed index demonstrates `$ref`-based composition,
and `openapi.yaml` is a bundled root spec used directly by Scalar for broad hosting compatibility.

## Publish to GitHub Pages

In repository settings:

1. Open **Settings → Pages**
2. Set **Source** to deploy from branch `main`
3. Set folder to `/docs`

Then your pages will be available as:

- `https://<owner>.github.io/<repo>/` → docs page
- `https://<owner>.github.io/<repo>/api-reference.html` → Scalar API reference

---

This repository is intentionally lightweight so you can use it as a starter template.