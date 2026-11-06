# grill-me-back

A skill for Claude Code: after the AI did the work, it asks you questions about it, one at a time, until you understand it. Ends with a short debrief of solid, shaky and missing parts.

## Install

Claude Code plugin:
```
/plugin marketplace add aprozo/grill-me-back
/plugin install grill-me-back@grill-me-back
```

Or copy the skill (Claude Code, opencode):
```
git clone https://github.com/aprozo/grill-me-back
cp -r grill-me-back/skills/grill-me-back ~/.claude/skills/
```

## Use

```
/grill-me-back                      # asks for the mode
/grill-me-back main..HEAD standard  # scope and mode
```
Modes: `quick` (~5 questions), `standard` (~12–15), `defense` (standard plus a skeptical colleague).

## License

MIT
