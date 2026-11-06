# Pixel Office

A free, MIT-licensed BLKC Kit: a living pixel-art office for your project. Your agents and tasks become characters and quests.

## Run it

```bash
npx @blkc-code/cli@latest dev
```

This opens a preview in your browser and reloads when you save. Click someone in the office to see what they are doing. The Every Block page shows each web Block with this theme.

## Make it your own

Everything is in `kit.json`:

- **Colours and fonts:** `theme`.
- **Words and sections:** `content.pages`.
- **The team and quests:** the `office` Block's `agents` and `tasks`.
- **The building:** give the `office` Block `cols`, `rows`, `rooms`, `doors` and `furniture`. Leave them out for the standard layout.

An agent's `state` is one of `working`, `thinking`, `blocked`, `reviewing`, `idle`, `done` or `away`. Furniture types are `desk`, `coffee`, `water`, `sofa`, `plant`, `board`, `shelf`, `server`, `table` and `rug`.

## Connect real work

While `blkc dev` is running, anything can update the office by writing `office-state.json` beside `kit.json`:

```json
{
  "agents": [{ "id": "nova", "name": "Nova", "state": "blocked", "task": "Needs a password" }],
  "tasks": [{ "title": "Ship it", "state": "doing" }]
}
```

A script, a build or a hook from your coding agent can write that file. BLKC does not connect to any agent for you yet.

## Put it on your own site

```js
import { readFileSync } from "node:fs";
import { renderToHTML } from "@blkc-code/render-web/server";

const kit = JSON.parse(readFileSync("kits/pixel-office/kit.json", "utf8"));
const { html } = renderToHTML(kit, "home");
```

Then, on the page, add `@blkc-code/render-web/styles.css` and call `mountCanvasBlocks()` from `@blkc-code/render-canvas`, or load its `runtime.js` in a script tag.

## Credits

Inspired by [Pixel Agents](https://github.com/pixel-agents-hq/pixel-agents) by Pablo De Lucca, MIT licensed. See [NOTICE](./NOTICE). The art here is original.
