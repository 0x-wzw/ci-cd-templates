# 0x-wzw Reusable CI/CD Workflows

## What This Is

Standardized workflow templates extracted from the best patterns across your portfolio.

## How to Use

1. Copy `.github/workflows/` files into target repos
2. Use `call-<workflow>.yml` as thin wrappers that delegate to reusable workflows stored in a **central repo**
3. Or copy inline — see each workflow's `usage:` section

## Workflows

| Workflow | Source Pattern | Replaces | Target Repos |
|----------|---------------|----------|--------------|
| `security-gate.yml` | NexusCosmos + oasis-v2 + october-workspace | 3 identical copy-paste files | NexusCosmos, oasis-v2, october-workspace, any new repo |
| `node-standard.yml` | paperclip_0xwzw + zodiac-v3 | guardgenius, FMCG-Order-dashboard, radikale-Konzept-landing | All Node repos |
| `python-standard.yml` | hermes-agent (uv-based) | Any Python repo without CI | Python repos |
| `docker-build.yml` | paperclip_0xwzw + zodiac-v3 + hermes-agent | Fragmented Docker builds | All repos with Docker |
| `release-engineering.yml` | paperclip_0xwzw | zodiac-v3, any product repo | Product-grade repos |
| `deploy-cloudflare.yml` | intelligence-teoh | intelligence-site (rewrite) | Static sites |

## Migration Priority

1. **Fix broken/deprecated** — NexusCosmos `::set-output`
2. **Standardize security gates** — Deduplicate 3 identical workflows
3. **Node version lock** — Standardize on Node 20 LTS
4. **Add CI to strategic repos** — voidtether, scoutforge, neuroswarm, superpowers-0xwzw, nexys
5. **Add Dependabot + CodeQL** — All repos with CI
