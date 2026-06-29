# Content Quality Gates

Read this when creating, auditing, or polishing Khopilot scripts, hooks, captions, carousels, or Threads posts.

In this Claude Code build the gates are **real, invocable skills**, not a copied static pack. This reference holds the Khopilot-specific pass/kill criteria; the skills do the actual rewriting.

## Position

These gates do not choose the content idea. Khopilot strategy chooses the lane, vehicle, route, and target metric. The gates make the chosen idea publishable.

Order (each line is a skill you can invoke):

1. `viral-hooks`
2. `storytelling`
3. `dumbify`
4. `anti-ai-writing`
5. voice DNA — bundled inside `content-skills`

Shortcut: invoke `content-skills` to run all five in their designed order in one pass.

## Gate 1 - Viral Hooks (`viral-hooks`)

Use for the first 1-2 seconds of Reels, carousel slide 1, first line of Threads, and opening caption line.

Pass criteria:

- Topic is clear immediately.
- The right viewer knows "this is for me."
- There is a concrete curiosity gap.
- Contrast is specific, not hollow.
- No empty wrappers like "POV:", "let me explain", or "you won't believe."

Khopilot example:

- Strong: "Google Maps buna yol diyor. Motorcu buna karakter testi diyor."
- Weak: "Bugün size çok ilginç bir yoldan bahsedeceğim."

## Gate 2 - Storytelling (`storytelling`)

Use for talking-head, route lore, build-in-public, and absurd mini-drama content.

Pass criteria:

- Beats move with `but` or `therefore`, not "and then."
- There is a clear last line worth sharing.
- Real details only. Do not invent founder stories, numbers, or events.
- Runtime budget holds: 30s is about 60-75 spoken words.

Skip heavy use for pure mechanical demos.

## Gate 3 - Dumbify (`dumbify`)

Use for explainers, product-proof, technical carousel, and any dense caption.

Pass criteria:

- Hook is easy enough for a 6th-grade reading level.
- Body is easy enough for an 8th-grade reading level.
- One idea per sentence.
- Jargon is used only if the audience knows it.
- Abstract claims become concrete examples.

Khopilot translation:

- Instead of "nöro-duyusal kreatif pre-test", say "hangi video daha canlı duruyor?"
- Instead of "route intelligence", say "virajı geç görmeden önce uyarı."

## Gate 4 - Anti-AI Writing (`anti-ai-writing`)

Use as final filter on all written copy: captions, carousel text, Threads, Story prompts, and pinned profile text. Use lightly on spoken scripts.

Pass criteria:

- No generic AI-ad words: ultimate, revolutionary, seamless, game-changing, elevate.
- No hollow "not X, but Y" unless the Y is concrete and the body delivers it.
- Specific scenes beat category claims.
- No over-polished brand manifesto voice.
- Reads like a person who rides/drives and has a take.

Khopilot examples:

- Strong: "D915'te viraj bitmiyor, ego bitiyor."
- Weak: "Khopilot revolutionizes your premium driving experience."

## Gate 5 - Voice DNA (inside `content-skills`)

Use when the account has enough real posts/transcripts. Until then, mark voice as unverified.

Starting voice:

- Turkish-first.
- Direct.
- Natural, not corporate.
- Can be slightly dirty or absurd.
- Sounds like motor/car culture, not SaaS copy.

Once 20 real posts or transcripts exist, build a voice profile from them and update this reference.

## Required Audit Block

Every content package should end with:

```text
QUALITY GATES
Viral hook: pass / revise
Story: pass / not applicable / revise
Dumbify: pass / revise
Anti-AI: pass / revise
Voice DNA: unverified / pass
Final action: publish / regenerate hook / rewrite caption / cut body
```

## Kill Rules

Do not ship if:

- The topic is not clear in 2 seconds.
- The content could belong to any generic motivation or car account.
- The caption is mostly polished brand words.
- A story is written as real but has no real beats.
- The joke is funny but has no route, vehicle, or Khopilot connection.
