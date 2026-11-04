# Catalog tag vocabulary

Canonical tags for `tags` in `data/grokgames.json`. Tags are lowercase slugs (`a-z0-9-`, max 32 chars).
New free-typed tags are still allowed (Igor's choice, 2026-11-04); prefer a canonical tag when one fits.

Counts are games carrying the tag as of 2026-11-04.

## Players

| tag | games | meaning |
|---|---|---|
| `multiplayer` | 36 | Online play with other people |
| `2-player` | 12 | Local 2P on one device: split-screen, same keyboard, couch, pass-and-play. Only when the source clearly says so |
| `co-op` | 3 | Cooperative play (online or local) |
| `mmo` | 2 | Persistent massively-multiplayer world |

## Genre

| tag | games | meaning |
|---|---|---|
| `racing` | 0 |  |
| `shooter` | 0 |  |
| `platformer` | 0 |  |
| `puzzle` | 0 |  |
| `strategy` | 0 |  |
| `rpg` | 1 |  |
| `sports` | 0 |  |
| `horror` | 2 |  |
| `sandbox` | 3 |  |
| `idle` | 6 |  |
| `roguelite` | 3 |  |
| `cards` | 4 |  |
| `fighting` | 1 |  |
| `simulation` | 2 |  |
| `adventure` | 2 |  |

## Other

| tag | games | meaning |
|---|---|---|
| `decomp` | 121 | Decompilation / recompilation / WASM port / preservation of an existing game |
| `rom` | 63 | Needs or runs original ROM / disc / game files |
| `mobile` | 15 | Touch controls work on phones |
| `cozy` | 7 | Relaxed, low-stress |
| `retro` | 2 | Retro / 8-16-bit style |
| `demo` | 8 | Demo, prototype or very thin slice |
| `requires_login` | 0 | Login or account needed before play (also set the `requires_login` field) |

## Site / source tags (always visible in the feed)

Where the game is hosted or was found. Keep them; Igor said not to hide site tags.

| tag | games |
|---|---|
| `itchio` | 107 |
| `crayon` | 18 |
| `wavedash` | 6 |
| `gameer` | 3 |
| `crazygames` | 1 |
| `ryft` | 1 |
| `vibegamedev` | 7 |
| `agentgames` | 11 |
| `genex` | 5 |
| `spawn` | 5 |
| `sandscape` | 5 |
| `gamefoundry` | 3 |
| `tesana` | 3 |
| `playgama` | 3 |
| `wasmarcade` | 2 |
| `bitmagic` | 1 |
| `soonlab` | 1 |
| `aigameshare` | 1 |
| `imaginestudio` | 1 |
| `origozero` | 1 |
| `neta` | 1 |
| `zevio` | 1 |
| `astrocade` | 1 |
| `jig` | 1 |
| `doszone` | 1 |
| `playmachine` | 1 |
| `mindblown` | 1 |
| `lolo` | 1 |
| `nimblefox` | 1 |
| `claude-artifact` | 1 |
| `chatgpt-site` | 1 |
| `remix` | 2 |

## Media tags (kept in data)

- `rec`: the clip was recorded by us (daily scan media rule depends on it).
- `screenshots`: card shows a screenshot slideshow instead of a clip (scan media rule depends on it).

## Merge map (old -> canonical)

| old | canonical |
|---|---|
| `preservation` | `decomp` |
| `port` | `decomp` |
| `recompiledgames` | `decomp` |
| `webassembly` | `decomp` |
| `wasm` | `decomp` |
| `roguelike` | `roguelite` |
| `card-battler` | `cards` |
| `deckbuilder` | `cards` |
| `incremental` | `idle` |
| `clicker` | `idle` |
| `highscore` | `leaderboard` |
| `Mystery / Thriller (any uppercase)` | `lowercase` |

## Removed tags

- `pc` / `PC`: too common to be useful (Igor, 2026-11-04). Platform info stays in the `platforms` field.
- Model tags `opus-5.5`, `astra`, `sonnet-5.5`: duplicate of `made_with`.
- `godot` / `unity` when the `engine` field already says the same.

Exception: rows whose tags mirror Igor's own feed overrides (`/workspace/overheard/igor-overrides-applied.json`) keep his tags until he says otherwise.

## Engine buckets

`engine` holds one of: Three.js, Godot, Unity, Unreal, Phaser, Babylon.js, Canvas/2D, WebGPU, Emscripten/WASM, ChatGPT, Claude artifact, Crayon, Other, or null (unknown).
The original detailed value is kept in `engine_detail` when it differs from the bucket (e.g. `Svelte + three.js`, `PCSX2 (WebAssembly)`, `Spawn`).
Rules: three.js / React Three Fiber -> Three.js; native code compiled to WebAssembly (Emscripten, Rust/WASM, .NET/FNA, TeaVM, Pyodide, decomp/recomp ports) -> Emscripten/WASM; plain JS WebGPU / wgpu -> WebGPU; PixiJS / Canvas / plain JS / Rive -> Canvas/2D; hosted builders (Spawn, Sandscape, Genex, mindblown.ai ...), native-only and rare engines -> Other.
