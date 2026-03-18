# Cloud Infra Reports

Static GitHub Pages site for viewing cloud infrastructure scan reports per company.

## Structure

```
index.html                  ← main page (deploy this)
data/
  companies.json            ← manifest: list of all companies
  k2partnering/
    infra.json              ← technical infra scan output
    ai.json                 ← AI analysis output
  acme/
    infra.json
    ai.json
```

## Adding a new company

1. Create a folder under `data/` using a URL-safe slug (e.g. `acmecorp`)
2. Drop `infra.json` and `ai.json` into that folder
3. Add one line to `data/companies.json`:

```json
[
  { "id": "k2partnering", "name": "K2 Partnering", "domain": "k2partnering.com" },
  { "id": "acmecorp",     "name": "Acme Corp",      "domain": "acmecorp.com" }
]
```

4. `git add . && git commit -m "add acmecorp" && git push`

The selector in the header updates automatically.

## GitHub Pages setup

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set Source to `Deploy from branch` → `main` → `/ (root)`
4. Your site will be live at `https://<you>.github.io/<repo>/`

## Direct links

Each company report is directly linkable via query string:

```
https://<you>.github.io/<repo>/?company=k2partnering
```
