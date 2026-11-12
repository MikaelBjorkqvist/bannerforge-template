# BannerForge add-on template

Template repository for BannerForge add-ons for Minecraft Bedrock Edition. Each mod lives in its own repo created
from this template (see `docs/decisions/0001-repo-per-mod.md`).

## New mod from this template
1. On GitHub: **Use this template → Create a new repository** named `bannerforge-<mod>`.
2. `npm run init -- <mod_id> "BannerForge: <Name>" "<one-line description>"` — sets the id and generates fresh UUIDs.
3. Commit, push, and CI builds the first `.mcaddon`.

## Commands
| Command | What it does |
| --- | --- |
| `npm install` | Install TypeScript and Script API type definitions |
| `npm run check` | BannerForge validator (namespace, lang keys, textures, stable APIs, no vanilla overrides) |
| `npm run typecheck` | TypeScript type-check against the pinned Script API |
| `npm run build` | Build `dist/<ns>_<id>_BP` and `_RP` with generated manifests |
| `npm run package` | Create `dist/<ns>_<id>-<version>.mcaddon` |
| `npm run deploy` | Copy built packs into Minecraft's development pack folders (`-- preview` for Preview) |
| `npm run dev` | check + build + deploy |
| `npm run release` | check + typecheck + build + package |
| `npm run bump -- patch\|minor\|major` | Bump version and open a CHANGELOG section |

## Releasing
`npm run bump -- minor`, write the CHANGELOG entries, commit, then `git tag vX.Y.Z && git push --tags`.
The Release workflow publishes a GitHub Release with the `.mcaddon` attached.

## Requirements
Node.js 22+. Minecraft Bedrock for Windows (GDK build, 1.21.120 or later) for local deploys.

Not an official Minecraft product. Not approved by or associated with Mojang or Microsoft.
