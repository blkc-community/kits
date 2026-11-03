# Public Records Kit

Bundles the CSV/JSON parser and BGE Small Embedder blocks so civic organisations can ingest raw public datasets and build search-ready indexes.

## Included Blocks

- `parser-csv-json@0.1.0`
- `embedder-bge-small@0.1.0`

## Flow

1. Parse raw CSV/JSON exports into normalised records.
2. Generate lightweight embeddings for search and clustering.
3. Persist vectors to a downstream index of your choice.

The manifest lives in `manifest.json`; update it when you change block versions or configuration defaults.
