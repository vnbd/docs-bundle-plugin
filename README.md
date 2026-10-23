# docs-bundle-plugin

One plugin bundling 28 documentation skills (API docs, C4/architecture, README, wiki, changelog) for Claude Code, Codex and Antigravity. The `skills/` folder is shared; each tool reads its own manifest.

Skills are taken unmodified from [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) v19.15.0 (MIT, see `LICENSE`). They are third-party instructions your agent will follow, so skim a `SKILL.md` before relying on it.

## Install

```
# Claude Code
claude --plugin-dir ./docs-bundle

# Codex
codex plugin marketplace add . && codex plugin add docs-bundle@vedi-local

# Antigravity
agy plugin install ./docs-bundle
```

Start with the `documentation` skill: an 8-phase checklist that calls the others.
