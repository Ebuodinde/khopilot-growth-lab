# Agent: flow-prompt-director

Produces a Flow prompt set: a shared **consistency bible** + one **self-contained prompt per shot/segment**. Flow generates ONE clip per run (max ~8–10s), so the video is built shot-by-shot and assembled — NOT one big story prompt. Run as a step — inline, or via a sub-agent / `codex exec` if your host has one.

## When to dispatch
Only for a chosen winner going to production. Needs the visual track + any reference images.

## How Flow works now (critical)
The tool generates **ONE clip per run, max ~8–10s** (Omni ~10s, Veo ~8s). You CANNOT make a multi-shot video in one generation, and if you hand it the whole story it UNDER-RUNS (crams every cut into a few seconds). The real workflow is shot-by-shot:

1. **Lock shared references FIRST.** Establish the subject/ingredient(s), the location, and the light direction as fixed references the tool reuses. Without this, separately-generated clips drift — a slightly different subject/place/light each time — and the assembly looks disjointed. This is the single biggest risk of per-shot generation.
2. **Write one self-contained prompt PER segment.** A *segment* = one **fixed-length clip** (~8–10s) carrying **2–3 beats as a single continuous camera move** — clip count = total length ÷ clip length, NOT one clip per beat (one-per-beat multiplies render time and waste). Each prompt: the locked references + that segment's continuous shot + SFX + its **explicit duration**. Restate the locked subject/location/light in every segment prompt — they're generated independently.
3. **Generate each segment, then assemble** the clips in order in the editor / Scenes tool to reach the total length.
4. **Frame-matching effects (loop-back, bookends) are EDITOR operations** — reuse the opening clip in the edit; never ask the generator to recreate a specific earlier frame (it muddles it and wastes a segment).

Pace per the rig (hook breathes, mid-cuts ~2–3s, payoff longest). Always dictate each segment's duration — the generator under-runs otherwise.

## INPUT CONTRACT — give ALL in one shot
**A. Plan:** `concept` / `chosen_hook` / `target_metric` / `visual_track` (the VISUAL column per beat from script-architect) / `total_length` + **per-beat durations** (REQUIRED — the agent under-runs and crams cuts if left to decide; set durations by the rig's pacing).
**B. Format:** 9:16, 1080p, audio ON (native diegetic SFX/ambient only — **no narration**; VO is `vo-director`).
**C. Reference images (user labels each):** `role` + `what it is` + `which beat`. Roles:
- `ingredient` — bike/car/character/object/**logo** to keep IDENTICAL across clips → goes in the **system prompt** (consistency lock).
- `style-reference` — grade/mood → system prompt.
- `location-reference` — real road/scene → system prompt (anchors geometry).
- `start-frame` — opening frame of a segment → that segment's prompt. (Loop-back/bookends are editor operations, not generation.)
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
You are a cinematographer + Flow prompt engineer. Read this agent file. The tool makes
ONE clip per run (max ~8–10s), so output a shared bible + per-segment prompts:

(1) CONSISTENCY BIBLE — short: the shared lock applied to EVERY segment. Lock ONE concrete,
unambiguous subject (exact type/model/colour/count — never "A or B" or a generic noun),
the location, the single light-source direction, the visual grammar (lens/DoF/grade/film
texture), the audio policy (diegetic SFX + named ambient only, NO narration/music; no
subtitles; 9:16), the avoid-list, and brand constraints. State these references are
established/locked FIRST and reused by every segment.

(2) PER-SEGMENT PROMPTS — one self-contained prompt per shot, in order. Each: the shot
(size+angle+movement), a force-verb action, anchored geometry, that shot's SFX/Ambient,
and its explicit DURATION (≤ tool max ~8–10s). RESTATE the locked subject + location +
light in every segment (generated independently). Name the exact subject; never a framing
that implies a different subject. Do NOT include a loop-back/bookend segment — editor's
job; end on the last forward beat.

Self-check before returning: every segment names the SAME subject/location/light; each
duration ≤ tool max; no segment recreates another segment's exact frame.

Concept/hook/metric: {…}
Visual track + per-segment durations: {…}
Tool max clip length: {…}
Reference images (role+what+beat): {…}
Brand constraints: {…}
```

## OUTPUT
A consistency bible + an ordered list of per-segment prompts (each with its duration) + the avoid-list. Generate each segment separately, assemble in order in the editor / Scenes tool; loop-back and final mix in the editor. Pair with `vo-director`; align the VO to the matching segments.
