---
name: grill-me-back
description: Reverse interview - the AI quizzes the USER on work the AI already did (e.g. a YOLO / auto-accept session, a branch, a PR, an analysis) until the user really understands it themselves, well enough to explain it, change it and debug it. Use for /grill-me-back, "quiz me on what you did", "test my understanding of this branch", "make sure I understand this code", "I don't want to use code I don't understand", or before presenting or handing in AI-made work. Not for stress-testing a plan before building (that is a different, plan-first kind of grilling).
allowed-tools: Read, Grep, Glob, Bash(git log *), Bash(git diff *), Bash(git show *), Bash(git status *), Bash(git merge-base *)
---

# grill-me-back

The AI did the work. Now the user must really understand it: what it does, why, and how to tell when it's wrong. **You ask, they answer.** No opening summary, and never your answer together with the question.

## Prepare (silently)

Finding facts is your job, never the user's. Before your first message, read the project: README, layout, `git log`, `git diff <base>..HEAD`, the changed files, and the conversation if there is one (trust git and files first; chat may be compacted). Don't say that you are reading.

Map the work as a **process**: the steps in order, what goes in and out of each, why each step is there, its assumptions, and how the result is checked. Mark weak spots: guessed numbers, hacks, skipped tests, untested steps. Keep facts and guesses apart; your map can be wrong.

## Start

`$ARGUMENTS` may give scope and mode, e.g. `main..HEAD quick`. If the mode is given, your first message is the first question. If not, one line: *"Quick, standard or defense? (standard if you don't care)"*. Quick ≈ 5 questions, standard ≈ 12–15, defense = standard plus you as a skeptical colleague.

## Grill

Walk the process map. **One question per turn**, under 40 words, plain English, no praise or filler. Per step: what → why → what if → how do you know it's right → debug (*"result is 2× too high — which step do you suspect?"*). Ask about steps and ideas, not lines or variable names. Let them find the weak spots with open questions; never point at them with yes/no questions. More ideas: `references/question-bank.md`.

Users type little; a few words is a fine answer. Don't ask them to run commands or open files. Describe the step, or paste ≤5 lines if the point is in the code.

Judging answers:
- "Right." only for a reason or a consequence. An echo of what you said, or a guess phrased as a question, gets "why?".
- Partly / wrong → say so, give a small hint (the step or a counterexample), let them retry. Second miss → explain in ≤3 sentences, then ask them to say it in their own words.
- They disagree with your map → check again before judging. They may be right.
- "It matches the expected value" is not proof, for them or for you.
- Your own mistake → let them try first, then say plainly it was yours. Asked "was this a good choice?" → say what you really think.
- Don't fix code during the session.

Done when every step on the map is solid, shaky or a gap, or the question budget is used.

## Debrief

About 20 short bullets, only what came up in the session:

```markdown
# grill-me-back — <project>, <date>
## What was done (in your words)
## Solid / Shaky / Gaps
## Weak spots in the work (step → fix or justify)
## Questions to check yourself later (⚠ = shaky)
## Next steps
```

Offer to save it to `GRILL_ME_BACK.md`, then offer a re-grill on shaky steps or a defense round.
