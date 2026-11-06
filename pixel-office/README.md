# Pixel Office

A free, MIT-licensed BLKC Kit: a living pixel-art office for your project. Your agents and tasks become characters and quests.

## Run it

```bash
npx @blkc-code/cli@latest dev
```

This opens a preview in your browser and reloads when you save. Click an agent in the office to see what it is doing. The Every Block page shows each web Block with this theme.

## Make it your own

Everything is in `kit.json`:

- **Colours and fonts:** `theme`.
- **Words and sections:** `content.pages`.
- **The team and quests:** the `office` Block's `agents` and `tasks`.
- **The building:** give the `office` Block `cols`, `rows`, `rooms`, `doors` and `furniture`. Leave them out for the standard layout.

An agent's `state` is one of `working`, `thinking`, `blocked`, `reviewing`, `idle`, `done` or `away`. Furniture types are `desk`, `coffee`, `water`, `sofa`, `plant`, `board`, `shelf`, `server`, `table` and `rug`.

## Use it as an app

`blkc dev` opens a full-screen app at `/office`. Add agents, move quests on the board, and changes save to `office-state.json`. Adding that file to `.gitignore` keeps your day-to-day status out of the repo.

## Connect your agents

Any agent on your machine can join:

```bash
npx @blkc-code/cli@latest office connect claude   # MCP, plus automatic updates
npx @blkc-code/cli@latest office connect cursor   # or vscode, or gemini
npx @blkc-code/cli@latest office connect codex
npx @blkc-code/cli@latest office connect other    # any other MCP agent
```

Then restart the agent. MCP agents report when they choose to, so ask yours to use the office tools. Anything else can run a command:

```bash
npx @blkc-code/cli@latest office set "My Agent" working --task "Building the page"
```

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
