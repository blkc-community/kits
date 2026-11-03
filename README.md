# BLKC Kits

Kits package blocks into ready-to-run workflows. Each kit keeps a manifest describing its dependent blocks and configuration expectations.

Use the CLI to scaffold a kit:

```
bun --bun packages/cli/dist/index.js kit create <kit-id>
```

Publishing a kit adds it to `registry/kits.json`.
