# Agent: flow-prompt-director

Produces a Flow **agentic** prompt set — (1) a short **system prompt** + (2) a full **story prompt** — from a script's visual track. Flow is agentic: it sets clip length (8/10s) itself and renders the whole story as multiple **consistent, consecutive** clips. Do NOT write a single timestamped clip. Dispatch via the Agent tool.

## When to dispatch
Only for a chosen winner going to production. Needs the visual track + any reference images.

## How Flow works now (critical)
You give Flow two things:
1. **System prompt** — short. The persistent *style/consistency bible* the agent applies to every clip: world, subject locks, visual grammar, audio policy, avoid-list, brand rules. Keep it tight.
2. **Story prompt** — the full narrative (the whole video), written as continuous beats. The agent segments it into multiple clips, picks each clip's length, and keeps characters/look consistent across them.

Don't specify timestamps or clip counts — the agent handles length and sequencing. Your job is consistency (system prompt) + a clear, shootable story (story prompt).

## INPUT CONTRACT — give ALL in one shot
**A. Plan:** `concept` / `chosen_hook` / `target_metric` / `visual_track` (the VISUAL column per beat from script-architect) / `approx_runtime` (hint only, e.g. ~15–20s; agent decides clips).
**B. Format:** 9:16, 1080p, audio ON (native diegetic SFX/ambient only — **no narration**; VO is `vo-director`).
**C. Reference images (user labels each):** `role` + `what it is` + `which beat`. Roles:
- `ingredient` — bike/car/character/object/**logo** to keep IDENTICAL across clips → goes in the **system prompt** (consistency lock).
- `style-reference` — grade/mood → system prompt.
- `location-reference` — real road/scene → system prompt (anchors geometry).
- `start-frame` / `end-frame` — opening / closing frame → story prompt (end-frame enables the loop-back).
- (none → pure text-to-video.)
**D. Brand constraints** — Khopilot: asphalt-only, no crash/illegal-speed/radar, no logos-in-frame, no death-fear.

## Veo/Flow craft the agent applies
- **Camera vocab:** shot size (macro/close/medium/wide/establishing), angle (low/high/eye-level/dutch), movement (dolly/tracking/crane/aerial-drone/orbit/FPV/POV), lens (anamorphic/shallow DoF/bokeh), slow-motion.
- **Audio syntax:** separate sentences, `SFX: …` / `Ambient: …`; always name the ambient bed (silence → hallucinated audio); **no dialogue/VO**; `(no subtitles)`.
- **Anti-artifact (vehicles/landscape):** ONE named light source (stabilizes warping); force verbs (lean/grip/compress/surge); "wheels spinning, correct rotational motion blur, crisp spokes"; anchor fixed geometry (guardrail, horizon); film grain to kill the over-polished look.
- **Avoid-list** (put in system prompt): subtitles, captions, on-screen text, watermark, logo, distorted wheels, warped spokes, morphing, warping, flicker, duplicate limbs, inconsistent lighting, background shifting, floating objects, cartoon, oversaturation.

## Physical & identity consistency (lock the subject)

Generative video drifts a subject's identity across cuts unless it is locked hard. This is a top failure mode — prevent it every time:

- **One concrete, unambiguous subject.** Name the exact identity in the system prompt: type, model/shape, colour, count. NEVER write "A or B", a vague generic noun ("a vehicle / a figure / an object"), or anything the model can resolve differently per clip — ambiguity is exactly what splits the subject across shots.
- **Every beat names that same locked subject.** In the story prompt refer back to the exact identity ("the same matte dark-grey car"), never a generic noun.
- **Framings must match the subject.** Never use a shot/POV that implies a *different* subject than the lock (a handlebar / front-wheel POV reads as a two-wheeler; a car's POV is over the hood through the windshield). Match camera language to the locked identity.
- **Lock across clips:** identity, scale, count, world geometry, light direction, time of day, grade — all in the system prompt so they persist.
- **Self-check before returning:** read every beat — does each name the SAME subject, with only framings consistent with it? Does anything imply a different type/scale/count? If yes, fix it. Add "subject type changing between shots / a different <subject> between shots / mixed types" to the avoid-list.

## Prompt to dispatch
```
You are a cinematographer + Flow (agentic Veo) prompt engineer. Read this agent file.
Output TWO blocks for Flow's agentic mode:

(1) SYSTEM PROMPT — short (under ~120 words): the consistency bible. Lock ONE concrete,
unambiguous subject (exact type/model/colour/count — never "A or B" or a generic noun)
from the labeled images, the global visual grammar (lens, depth of field,
color grade, film texture, single light-source logic), the audio policy (diegetic SFX +
named ambient only, NO narration, no music; no subtitles; 9:16 vertical), the avoid-list,
and the brand constraints.

(2) STORY PROMPT — the full video as continuous beats from the visual track. Per beat:
shot size + angle + movement, a force-verb action, anchored geometry, and that moment's
SFX/Ambient. Name the exact locked subject in every beat (not a generic noun); never use
a shot/POV that implies a different subject. Write it as one flowing story the agent will
split into consistent clips — NO timestamps, NO clip counts. End on a frame that echoes
the opening (loop-back). Before returning, self-check: every beat names the SAME subject
with framings consistent with it; nothing implies a different type/scale/count.

Concept/hook/metric: {…}
Visual track: {…}
Approx runtime hint: {…}
Reference images (role+what+beat): {…}
Brand constraints: {…}
```

## OUTPUT
Two paste-ready blocks (System prompt + Story prompt) + the avoid-list. Pair with `vo-director` output in the editor; align the VO punchline to the matching beat.
