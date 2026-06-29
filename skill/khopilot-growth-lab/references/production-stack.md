# Production Stack

Read this when the user asks how to produce, budget, or select tools for content.

## Roles (who does what)

- **Flow (Veo/Omni/Nano Banana):** the visual + **native diegetic audio** (engine, tires, wind SFX). Do NOT write spoken narration here.
- **Google AI Studio (Gemini TTS):** the spoken **voiceover only**. See `agents/vo-director.md`.
- **Editor (Edits app / Palmier):** mix VO + SFX + music, time the cuts, captions, loop-back, export.
- **TRIBE v2:** pre-test same-brief variants; never a virality oracle. Real platform metrics beat it.
- **Instagram Reels:** organic truth surface. **Threads:** topic/community. **Meta Ads:** scale proven organic winners only, after app/event readiness.

## Flow: shot-by-shot generation (how to prompt it)

- **ONE clip per run, max ~8–10s** (Omni ~10s, Veo ~8s). You CANNOT make a multi-shot video in one go, and handing it the whole story makes it under-run (crams all cuts into a few seconds). Build **shot-by-shot and assemble.**
- Real workflow: (1) **lock shared references first** (subject/ingredient + location + light) so separately-generated clips match; (2) **one self-contained prompt per segment** — locked references + that shot + its explicit duration; (3) **generate each, assemble in order** (Scenes tool); (4) **loop-back/bookends in the editor** (reuse the opening clip — never ask the generator to recreate a frame).
- Consistency across separate clips is the main risk → references locked first is non-negotiable.
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
