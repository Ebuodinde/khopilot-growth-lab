# Agent: script-architect

Fills the 5×3 matrix for a chosen hook into a shootable script. Run as a step — inline, or via a sub-agent / `codex exec` if your host has one.

## When to dispatch
After `hook-smith` returns a chosen hook, to turn it into the full beat×channel script.

## INPUT CONTRACT
- `chosen_hook` — the 3-channel hook stack from hook-smith.
- `tenant` + `topic` + `target_metric` (same as hook-smith).
- `runtime` — target length (default 12–20s for new-audience reach).
- `format` — talking-head / B-roll+VO / on-screen-text / mixed.

## Prompt to dispatch
```
You are a short-form script architect. Read references/system.md in [skill dir].
Fill the 5 beat × 3 channel matrix for this video into a shootable script.
Rules: the hook beat's opening must earn the muted first 1.5s via at least one of — an
unresolved question, high visual/sensory stakes, or tight topic-audience relevance
(survival gate, system.md §3); avoid low-stakes/mundane/off-niche openings; all three
channels say the same thing (mute-first). Open a SPECIFIC loop in beat 2 and close
it in beat 4. Build uses "but/therefore", one idea per line,
zero fluff. Beat 5 places the metric trigger correctly for {target_metric} and adds a
loop-back (last 0.5s echoes frame 1). Keep spoken words to ~60–75 per 30s.

Chosen hook: {chosen_hook}
Tenant / topic / metric: {tenant} / {topic} / {target_metric}
Runtime: {runtime} | Format: {format}

Return: the filled matrix table, then a clean beat-by-beat shooting script (VISUAL /
VO line / TEXT overlay per beat), the open/close-loop callout, and the beat-5 CTA.
```

## OUTPUT
Filled matrix + beat-by-beat script. Feed VISUAL column to `flow-prompt-director`, VO column to `vo-director`, and the whole thing to `retention-editor`.
