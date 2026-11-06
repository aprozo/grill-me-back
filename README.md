# grill-me-back

An agent skill ([Agent Skills](https://agentskills.io) format): after the AI did the work, it asks you questions about it, one at a time, until you understand it. Ends with a short debrief of solid, shaky and missing parts.

## Install

Any agent ([skills CLI](https://github.com/vercel-labs/skills)):
```
npx skills add aprozo/grill-me-back
```

Or copy the folder: `~/.agents/skills/` (Codex and others) or `~/.claude/skills/` (Claude Code):
```
git clone https://github.com/aprozo/grill-me-back
mkdir -p ~/.agents/skills && cp -r grill-me-back/skills/grill-me-back ~/.agents/skills/
```

Claude Code plugin:
```
/plugin marketplace add aprozo/grill-me-back
/plugin install grill-me-back@grill-me-back
```

## Use

Ask for it ("grill me back"), or call it directly: `/grill-me-back` in Claude Code, `$grill-me-back` in Codex. Optional scope and mode: `/grill-me-back main..HEAD standard`.

Modes: `quick` (~5 questions), `standard` (~12–15), `defense` (standard plus a skeptical colleague).

## License

MIT
