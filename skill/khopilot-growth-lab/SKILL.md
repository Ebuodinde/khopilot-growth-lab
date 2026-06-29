---
name: khopilot-growth-lab
description: "Topic-agnostic short-form virality engine. Use to design, write, and audit watchable Reels/TikTok/Shorts content for ANY subject — engineering the scroll-stop, retention, and share-trigger rather than dumping ideas. Builds hooks, beat×channel scripts, retention-edit plans, Flow/Veo prompts, AI Studio voiceover specs, and metric reads. Khopilot (motor/car route culture, pre-launch) is the built-in default tenant. Trigger on requests for viral hooks, reel scripts, content systems, hook testing, Flow prompts, voiceover scripts, or metric reviews."
---

# Growth Lab — Short-Form Virality Engine

This skill is a **factory, not an idea list.** It builds the *rig* that produces watchable video for any topic, then pours a subject through it. The first tenant is **Khopilot** (pre-launch motor/car route culture), but the engine is topic-agnostic — swap the tenant, keep the rig.

## The only two things that move reach (Meta-confirmed)

Optimize for exactly these; everything else is secondary. (Full mechanics + sources: `references/algorithm-2026.md`.)

1. **Watch time** — the #1 ranking signal. Wins whether a post survives its seed test. Won by hook + retention.
2. **Sends per reach** (DM shares) — the strongest signal for reaching **non-followers**. The only mechanical path to "phenomenon." Won by engineering a *"send this to someone who…"* moment.

**Order is fixed — HOLD before SEND.** Clearing the <3s skip is a real precondition, but the opening can earn it through **more than one mechanism**: an unresolved question, high visual/sensory stakes, OR tight topic-audience relevance — none individually required. The measured failure is a *low-stakes + mundane + off-niche* opening. Relatability drives SEND (sharing after the watch), not HOLD (staying). Treat any single gate rule as a **risk flag, not a verdict** — theory-based pre-ranking has been unreliable in both directions; resolve it by testing diverse bets against real skip/completion/sends. See `references/system.md` §1 + §3 and `references/calibration.md`.

Hard truths baked into every output: ~half of views are **muted** → the hook must work on mute. **Follower count is not a gate** (signals are per-reach rates) → a new account can break out on one post. **Trending audio and hashtags are not reach levers** → don't lean on them. Stay **recommendation-eligible**: original, no third-party watermark, audio present, under 3 min, account in good standing.

## The Rig (canonical — read `references/system.md`)

Every video is a **5 beat × 3 channel** matrix:

- **Beats:** 1) Hook (0–1.5s, scroll-stop) · 2) Lock/re-hook (→3s, open the loop) · 3) Build (~70%, value + "but/therefore") · 4) Payoff (close the loop) · 5) Button + loop-back (CTA for the chosen metric).
- **Channels:** Visual · Audio · Text. In the **Hook beat all three say the same thing** (stacking/redundancy) so any one carries it alone. They may diverge after the hook lands.

The **4 transferable writing moves**: decide-at-frame-1 · open a *specific* gap · hold by value-per-second + causality · over-pay the loop you opened.

## The Factory Loop (how to run a job)

Each file in `agents/` is a ready playbook (role + input contract + prompt). Run them as steps in order — apply each inline, or hand it to a sub-agent / parallel exec if your host has one (e.g. Codex `codex exec`). Default order:

1. `hook-smith` — generate N hooks across the taxonomy, score for watch-time + send potential, return top 3. (`agents/hook-smith.md`)
2. `script-architect` — fill the beat×channel matrix for the chosen hook; design for mute-first. (`agents/script-architect.md`)
3. `retention-editor` — cut/pattern-interrupt/loop-back plan. (`agents/retention-editor.md`)
4. Production (only for a chosen winner): `flow-prompt-director` (a shared consistency bible + per-segment shot prompts — build shot-by-shot at ~8–10s per clip and assemble; references locked first) + `vo-director` (voiceover spec mapped to the AI Studio UI fields). (`agents/flow-prompt-director.md`, `agents/vo-director.md`)
5. After publish: `metric-judge` — read Insights, decide clone/revise/kill. (`agents/metric-judge.md`)

For a small job, run the relevant role only. For quick asks, apply the rig inline.

## Reference Routing

- The rig (matrix, levers, hook thresholds, eligibility): `references/system.md`.
- Algorithm mechanics + sources: `references/algorithm-2026.md`.
- Hook taxonomy + generate-many + scoring: `references/hook-engine.md`.
- Writing quality gates (self-contained criteria): `references/content-quality-gates.md`.
- Output skeleton: `references/content-brief.md`.
- Metric interpretation: `references/metrics-intake.md`.
- Prediction-vs-data discipline + standing abstracted inferences: `references/calibration.md`.
- Follower-growth sprint operating procedure (what to attend to across a campaign, not a single video): `references/growth-campaign.md`.
- **Khopilot tenant pack** (lanes, voice, idea bank, tools): `references/prelaunch-growth-system.md`, `references/prelaunch-idea-bank.md`, `references/production-stack.md`.

Load only what the current request needs.

## Tenants

A **tenant** is the subject the rig is poured through: its lane/positioning, voice, constraints, and idea bank. Khopilot is the default (read the prelaunch-* references). For any other subject, ask for or infer the tenant's: positioning, audience, voice, hard constraints, and target metric — then run the same rig.

**Khopilot constraints (always on for this tenant):** pre-launch → no install CTA; optimize follows/saves/sends/comments/profile-visits/beta-demand. Turkish-first, natural, can be slightly absurd/dirty. Avoid death/crash fear, illegal speed, radar evasion, generic AI-ad wording. Asphalt-guaranteed routes only.

## Quality Gates

Before shipping any script/caption, run the writing gates in order — viral hook → storytelling → dumbify → anti-AI → voice — applying the criteria + audit block in `references/content-quality-gates.md` inline. (If your host ships these as separate invocable skills, you may call those instead.) The rig chooses the structure and metric; the gates make the words publishable.

## Output Style

Concept work: compact tables + one detailed first pick. Execution work: copy-paste-ready prompts, scripts, captions. Metric reviews: lead with the clone/kill decision. Always name the **one target metric** per video and place its trigger at the structurally correct beat.
