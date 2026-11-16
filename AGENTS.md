# AGENTS.md — GameScrobbler Hackathon Addendum

> **Note for `gs-mono`:** `game-scrobbler/gs-mono` already has root `AGENTS.md`, `CLAUDE.md`, `.cursor/rules/agent-onboarding.mdc`, and `.mcp.json` (with `posthog`: `https://mcp.posthog.com/mcp`). Keep those intact and append this **Hackathon Rules** section rather than overwriting them. For the throwaway dry-run repo, keep this standalone file at the repo root.

## Confirmed `gs-mono` Stack & Commands (`pnpm@12.18.0`, Node 26)
- `pnpm install` · `pnpm db:generate` · `pnpm dev`
- `pnpm typecheck` · `pnpm lint` · `pnpm lint:ratchet` · `pnpm test`
- `pnpm build:front` · `pnpm build:back` · `pnpm build:worker`
- **PostHog MCP:** Already declared in `gs-mono/.mcp.json` (`https://mcp.posthog.com/mcp`)
- **Demo hosting:** Vercel Hobby (PR previews + production branch auto-deploy)

## Hackathon Rules (16 Nov – Divan Hackathon)
1. **One ticket, one branch:** Work only on your assigned GitHub Issue. Branch name: `gs/<issue-number>-<short-slug>`.
2. **Draft PR only:** Never merge your own or a human's PR. Open a **Draft PR** using `.github/PULL_REQUEST_TEMPLATE.md` and include `Fixes #<issue-number>`.
3. **Feature-flag demo risk:** Wrap incomplete user-facing changes behind a **PostHog Feature Flag** so the live Vercel demo URL stays unbroken at all times.
4. **Query PostHog MCP, don't guess:** For bug reports or regressions, inspect stack traces, exceptions, and session replays via PostHog MCP (`https://mcp.posthog.com/mcp`) before editing code.
5. **Respect GitHub Actions headroom (`~$3.70` left until ~Dec 1):** `gs-mono` runs heavy `code-quality.yml` and `security-scan.yml` workflows. Never push rapid redundant commits to open PRs, keep runners on `ubuntu-latest`, keep `concurrency.cancel-in-progress: true`, and skip CI on docs-only changes.
6. **Subscriptions only:** Do not configure API-billed coding keys, modify GitHub org/billing settings, or write secrets into files or commits.
