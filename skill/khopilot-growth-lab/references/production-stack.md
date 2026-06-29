# Production Stack

Read this when the user asks how to produce, budget, or select tools for content.

## Roles (who does what)

- **Flow (Veo/Omni/Nano Banana):** the visual + **native diegetic audio** (engine, tires, wind SFX). Do NOT write spoken narration here.
- **Google AI Studio (Gemini TTS):** the spoken **voiceover only**. See `agents/vo-director.md`.
- **Editor (Edits app / Palmier):** mix VO + SFX + music, time the cuts, captions, loop-back, export.
- **TRIBE v2:** pre-test same-brief variants; never a virality oracle. Real platform metrics beat it.
- **Instagram Reels:** organic truth surface. **Threads:** topic/community. **Meta Ads:** scale proven organic winners only, after app/event readiness.

## Flow is agentic (how to prompt it)

- You give Flow **two things**: (1) a short **system prompt** (style/consistency bible) + (2) a full **story prompt** (the whole video as continuous beats).
- **Flow sets clip length itself** (8/10s) and renders the story as **multiple consistent, consecutive clips** — do NOT hand-specify timestamps, cut counts, or per-clip length.
- Consistency (subject/ingredient/look) lives in the **system prompt**; the narrative + per-beat camera/action/SFX lives in the **story prompt**.
- Aspect **9:16**, **1080p**, audio **ON** (native diegetic SFX/ambient, **no narration** — VO is separate).
- Production prompts come from `agents/flow-prompt-director.md`. VO from `agents/vo-director.md` (maps to the real AI Studio UI: Scene / Sample Context / Audio Profile / Style / Pace / Accent / Voice / tagged text).

## Flow Credit Rules

Monthly budget: 1,000 Flow credits.

| Work | Credits |
|---|---:|
| Veo 3.1 Lite | 10 |
| Veo 3.1 Fast | 20 |
| Veo 3.1 Quality | 100 |
| Gemini Omni Flash 4s | 15 |
| Gemini Omni Flash 6s | 20 |
| Gemini Omni Flash 8s | 25 |
| Gemini Omni Flash 10s | 30 |
| Omni Flash video edit | 40 |
| 1080p upscale | 0 |

Use Quality only for pinned hero or proven winners. Draft with Lite/Fast.

## Monthly Allocation

- 2 big hero/pinned reels: about 280 credits.
- 10-12 quick viral tests: about 250 credits.
- 5-6 absurd tests: about 180 credits.
- 4 product-shadow/HUD proofs: about 120 credits.
- Mistake/retry reserve: about 170 credits.

## Production Package

Produce:

1. Hook and target metric.
2. 3 variants: natural, absurd, product-proof.
3. Flow prompt and negative prompt.
4. Overlay text.
5. Caption.
6. Threads version.
7. Story prompt.
8. Metrics template.
