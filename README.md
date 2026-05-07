# @mnemopay/toolkit

The MnemoPay agent toolkit — the capability layer that pairs with `@mnemopay/sdk`'s portable trust layer. One install pulls in the runtime, the specialist agents, and the perception/action surface an autonomous agent needs to do work.

```bash
npm install @mnemopay/toolkit
```

## What's in the box

| Category | Package | What it does |
|---|---|---|
| Runtime | `@kpanks/cli` | CLI runner — agent runtime entry point |
| Runtime | `@kpanks/api` | HTTP API server — `PraetorHTTP`, no Express |
| Runtime | `@kpanks/router` | Multi-LLM routing with prompt caching + Batch API |
| Runtime | `@kpanks/agents` | Agent orchestration core |
| Runtime | `@kpanks/sandbox` | Sandbox factory — Mock / Local / Docker (hardened) / Firecracker stub |
| Specialist | `@kpanks/coding-agent` | Coding agent — file/git/test tools + native unified-diff applier (16 tools) |
| Specialist | `@kpanks/research-agent` | Research agent — web search, source fetch, structured synthesis |
| Perception | `@kpanks/browser` | DOM-first browser automation (lazy `playwright-core`, Stagehand-shaped a11y outline) |
| Perception | `@kpanks/computer-control` | Computer-use session — audit + activity-bus streaming |
| Perception | `@kpanks/vision` | Native screen capture (PowerShell / `screencapture` / grim) + vision tools |
| Perception | `@kpanks/voice` | Native TTS — Kokoro 82M default + Azure Speech, license-family enforceable |
| Perception | `@kpanks/scrape` | Native fetch + SSRF guard + JSON-LD + sitemap + X.com syndication |
| Knowledge | `@kpanks/knowledge` | Knowledge base — vector + chunking |
| Knowledge | `@kpanks/tools` | Tool registry primitives |

## How it pairs with `@mnemopay/sdk`

`@mnemopay/sdk` is the **trust layer** — payments, memory, identity, Agent Credit Score (300–850), governance (FiscalGate, Article 12 audit bundles), and cross-rail portability. Every action your agent takes can be priced, signed, and audited.

`@mnemopay/toolkit` is the **capability layer** — what your agent uses to actually *do* things in the world.

You can use either alone or both together. Together they form the full MnemoPay agent platform.

```ts
import MnemoPay from "@mnemopay/sdk";
import { runMission } from "@mnemopay/sdk";          // governance
import { CodingAgent } from "@kpanks/coding-agent";  // capability

const agent = MnemoPay.quick("my-agent");
// ... charter + budget + tools, run via runMission
```

## On the package names

The toolkit ships under `@mnemopay/toolkit` as a meta-package; the underlying capability packages remain published at `@kpanks/*` for backward compatibility. New code should depend on `@mnemopay/toolkit` to get the curated set; advanced users can install individual `@kpanks/*` packages directly.

## Status

- **v0.1.0** — initial meta-package release. Pulls in 14 `@kpanks/*` packages at `^0.1.0`.
- The Praetor brand the toolkit grew out of has been retired in favor of the unified MnemoPay platform; see [project_mnemopay_platform_2026_05_06] for the consolidation plan.

## License

Apache-2.0. Built by J&B Enterprise LLC.

## Links

- **Site:** https://mnemopay.com/toolkit
- **SDK (trust layer):** https://www.npmjs.com/package/@mnemopay/sdk
- **GitHub (sub-packages):** https://github.com/mnemopay/praetor (legacy mono-repo, will sunset)
