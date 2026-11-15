# AGENTS.md

L3: **ITM** — the customer front end for the ITM store.

The company and consumer product name is **ITM**. Use that exact name in customer-facing branding and current documentation. The inherited folder, remote, and provider identifiers are technical compatibility names, not company names.

This repository owns the customer experience. The standalone MeritStore provider (`AgentDraven/merit-store`, restored Nov 14, 2026) owns the catalog, booking/checkout APIs and commercial state; MeritSubs owns identity and entitlements. Each provider keeps its own canonical `main`; merit-utils supplies shared utilities (PAR pins) only. Keep provider code out of this consumer. Update `cfg/providers.lock.json` and immutable utility pins together using `npm run providers:sync`, then validate against remote main before release. Do not create provider forks, new development branches, or sibling source imports for ITM.

- Design: `merit-demo docs/merit_demo_design.md`
- Usage: `merit-demo docs/merit_demo_usage.md`
- Plan SSOT: `merit-demo docs/IAR/MERIT_DEMO_ECOSYSTEM_PLAN.md`
- OSS CLI: sibling [merit-agent-skills](https://github.com/AgentDraven/merit-agent-skills) `merit.ps1` / `merit.sh` (pin via `%MYMERITAPP%\oss-bench.json`)

**Paths:** resolve `MYMERITAPP` → `oss-bench.json` → `demoFolder`; or `..\merit-agent-skills\merit.ps1 where`. Never hardcode `C:\MyMeritApp`.

**Skills host:** Hub **I** / `install.ps1 -Target Cursor` → `~/.cursor/skills` (not a full in-repo `.cursor` skill tree).

Public users use **merit.ps1** / **merit.sh** for scaffold/deploy; vault **scripts/merit.ps1** is only for private cert and operator-gate workflows.
