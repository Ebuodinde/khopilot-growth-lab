# Agent: hook-smith

Generates and scores a batch of hooks for one content idea. Dispatch via the Agent tool (general-purpose) with the prompt below filled in.

## When to dispatch
First step of any content job, or whenever a draft's opener is weak. For a quick ask you may run the logic inline instead.

## INPUT CONTRACT (give all of these)
- `tenant` — subject/brand context (default: Khopilot — read `references/prelaunch-growth-system.md` + `references/prelaunch-idea-bank.md`).
- `topic/angle` — the specific subject of this video.
- `target_metric` — one of sends / saves / comments / follows / completion.
- `awareness_level` — unaware / problem-aware / solution-aware / product-aware / most-aware.
- `constraints` — tenant hard rules (Khopilot: no install CTA, no crash-fear/illegal-speed, TR-first).

## Prompt to dispatch
```
You are a hook engineer. Read references/hook-engine.md and references/system.md in
[skill dir]. For the following job, generate 12 hooks across the taxonomy types
(label each with its type), apply the 70/20/10 split. Apply the survival GATE as a risk
flag: prefer openings that earn the muted first 1.5s via at least one of — an unresolved
question, high visual/sensory stakes, or tight topic-audience relevance. Flag (don't auto-
eliminate) only openings that are low-stakes AND mundane AND off-niche. THEN score on the
6-point rubric and return the TOP 3 with scores. For each of the top 3, write the hook as a
3-CHANNEL STACK: visual hook (frame-1 description), audio hook (spoken 5–10 words),
text hook (1–7 word on-screen headline) — all saying the same thing. Mute-first.

Tenant: {tenant}
Topic/angle: {topic}
Target metric: {target_metric}
Awareness: {awareness_level}
Constraints: {constraints}

Return: the 12 labeled hooks, the top-3 with scores, and each top-3 as a channel stack.
```

## OUTPUT
12 labeled hooks → top 3 scored → each top pick as visual/audio/text stack. The caller picks one and hands it to `script-architect`.
