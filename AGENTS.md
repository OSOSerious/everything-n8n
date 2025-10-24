# Repository Guidelines

## Project Structure & Module Organization
This repository stores production-ready n8n workflows grouped by automation domain. Flagship AI and SEO agents reside in directories such as `ai-overview-analyzer/`, `ai-overview-optimizer/`, `seo-data-analyst/`, and `ai-powered-seo-team/`. Each contains the primary workflow JSON (for example, `ai-overview-analyzer.json`), tool workflows prefixed `tool-`, screenshots, and a contextual `readme.md`. Legacy or community templates remain in alphabetical integration folders (`Activecampaign/`, `Slack/`, etc.), while `Code/` holds generalized workflow snippets. Reference guides live under `Documentation/`, and `workflows/` plus `workflows_backup/` store shared exports or staging copies.

## Build, Test, and Development Commands
Use the n8n CLI for round-tripping workflows:
- `n8n import:workflow --input ai-overview-analyzer/ai-overview-analyzer.json` — load a template into your instance.
- `n8n export:workflow --id <workflowId> --output ai-overview-analyzer/ai-overview-analyzer.json` — write back changes captured in n8n.
- `n8n start --dev --user-folder ~/.n8n` — run a local dev instance for interactive agent testing.

## Coding Style & Naming Conventions
Workflow JSON is formatted with two-space indentation and n8n’s default key ordering. Maintain existing filename patterns (`tool-*` for helper flows, `<Category>_<Verb>_<Trigger>.json` in `Code/`, kebab-case for new directories). Markdown README updates should stay instructional: prerequisites, numbered setup steps, usage notes, and embed PNG assets stored alongside the workflow.

## Testing Guidelines
Test within a sandboxed n8n project. Pin sample data on SERP, crawl, and LLM nodes to avoid costly external calls. When iterating on agent orchestration, trigger the main chat workflow, observe `Execute Workflow` hand-offs, and verify memory nodes retain context. Capture example execution exports or screenshots to share in PRs.

## Commit & Pull Request Guidelines
No Git history ships with this archive, so adopt a descriptive conventional-commit style (e.g., `feat(ai-overview-analyzer): add serpapi retry`). PRs should list affected directories, document credential or environment changes, and attach screenshots or exports showing successful runs. Update related files under `Documentation/` when behaviour changes.

## Security & Configuration Tips
Keep API keys and service credentials out of the repository—reference named n8n credentials instead. Note rate limits or new environment variables in the relevant `readme.md`, and surface dependencies (SerpApi, OpenAI, BigQuery, etc.) so operators can replicate configuration safely.
