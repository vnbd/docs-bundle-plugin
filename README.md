# docs-bundle-plugin

28 documentation skills (API docs, C4/architecture, README, wiki, changelog) packaged as one plugin for Claude Code, Codex/ChatGPT and Antigravity, plus a zip route for claude.ai.

The skills are copied unmodified from [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) v19.15.0 (MIT, see `LICENSE`). They are third-party instructions your agent will follow, so skim a `SKILL.md` before relying on it. Start with `documentation`: an 8-phase checklist that calls the rest.

## Layout

```
.claude-plugin/marketplace.json   Claude Code marketplace (name: vedi-docs)
.agents/plugins/marketplace.json  Codex / ChatGPT marketplace (name: vedi-docs)
docs-bundle/
  .claude-plugin/plugin.json
  .codex-plugin/plugin.json
  .antigravity-plugin/plugin.json
  skills/<name>/SKILL.md          28 skills, shared by every tool
```

## Claude Code

```
/plugin marketplace add vnbd/docs-bundle-plugin
/plugin install docs-bundle@vedi-docs
```

Skills are namespaced, e.g. `/docs-bundle:readme`. To test from a clone without installing: `claude --plugin-dir ./docs-bundle`.

The repo is private, so git must be authenticated (for example `gh auth login`).

## Claude (claude.ai)

claude.ai takes custom skills as zip files under Settings > Features, on Pro, Max, Team and Enterprise plans with code execution enabled. Upload is per user, not shared org-wide. Zip each skill folder:

```bash
cd docs-bundle/skills && zip -r readme.zip readme
```

## Codex

```bash
codex plugin marketplace add vnbd/docs-bundle-plugin
codex plugin add docs-bundle@vedi-docs
```

From a clone, use `codex plugin marketplace add .` instead.

## ChatGPT

OpenAI's plugins work in the ChatGPT desktop app and Codex through the same marketplace file. After adding the marketplace as above, restart the ChatGPT desktop app, open the Plugins Directory, choose `vedi-docs`, and install `docs-bundle`.

## Antigravity

```bash
git clone https://github.com/vnbd/docs-bundle-plugin && cd docs-bundle-plugin
agy plugin install ./docs-bundle
agy plugin validate docs-bundle   # expect 28 skills
```

## Status

Verified: the Antigravity manifest passes `agy plugin validate` (28 skills). The Claude Code, Codex and ChatGPT steps follow the vendors' current docs but have not been run against this repo. The claude.ai zip upload has not been tried.
