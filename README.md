# grill-me-back

An agent skill ([Agent Skills](https://agentskills.io) format): after the AI did the work, it asks you questions about it, one at a time, until you understand it. Ends with a short debrief of solid, shaky and missing parts.

## Why

An agent in auto-accept mode can write in an hour what would take you a week. If you can't explain it, change it or debug it, you can't use it. `grill-me` has the AI question you before the work; `grill-me-back` questions you after it.

```
AI:  Why is the efficiency correction applied before the background subtraction?
You: background is estimated from data, so it already includes the efficiency
AI:  Right. If the correction were applied after, what would happen to the yield?
You: too high?
AI:  Why?
```

## Install

<details>
<summary><strong>Claude Code</strong></summary>

```
/plugin marketplace add aprozo/grill-me-back
/plugin install grill-me-back@grill-me-back
```
</details>

<details>
<summary><strong>Codex</strong></summary>

```
codex plugin marketplace add aprozo/grill-me-back
codex plugin add grill-me-back@grill-me-back
```
</details>

<details>
<summary><strong>GitHub Copilot</strong></summary>

```
copilot plugin marketplace add aprozo/grill-me-back
copilot plugin install grill-me-back@grill-me-back
```
</details>

<details>
<summary><strong>Gemini CLI</strong></summary>

```
gemini skills install https://github.com/aprozo/grill-me-back.git --path skills
```
</details>

<details>
<summary><strong>Any other agent</strong></summary>

```
npx skills add aprozo/grill-me-back
```
or copy `skills/grill-me-back` into `~/.agents/skills/`.
</details>

## Use

The skill runs only when called: `/grill-me-back` (Claude Code), `$grill-me-back` (Codex). Optional scope and mode: `/grill-me-back main..HEAD standard`.

Modes: `quick` (~5 questions), `standard` (~12–15), `defense` (standard plus a skeptical colleague).

## License

MIT
