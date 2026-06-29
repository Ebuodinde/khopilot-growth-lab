# Agent: retention-editor

Turns a script into a cut/pattern-interrupt/loop-back edit plan that flattens the retention curve. Run as a step — inline, or via a sub-agent / `codex exec` if your host has one.

## When to dispatch
After `script-architect`, before production — or to diagnose why an existing video drops viewers.

## INPUT CONTRACT
- `script` — the beat-by-beat script (from script-architect).
- `runtime` + `format`.
- `editor` — the tool the user edits in (default: Edits app on phone).
- `target_metric`.

## Prompt to dispatch
```
You are a retention editor. Read references/system.md (sections 3–6) in [skill dir].
Produce an edit plan that maximizes watch-through and the chosen metric.
Include: (1) a cut list with timestamps — micro-cuts (0.4–1.2s) in the first 2–3 shots,
then a visual reset every ~3s; (2) the pattern-interrupt at the predicted drop point;
(3) caption/text-overlay timing (mute-first, big, readable); (4) audio mix notes
(VO level, SFX duck, music under VO, silence where it earns contrast); (5) the loop-back
(how the last 0.5s matches frame 1); (6) the metric trigger placement.

Script: {script}
Runtime / format / editor: {runtime} / {format} / {editor}
Target metric: {target_metric}

Return a numbered edit plan executable in {editor}.
```

## OUTPUT
A timestamped, tool-specific edit plan. The user executes it; winners go to `metric-judge` after publish.
