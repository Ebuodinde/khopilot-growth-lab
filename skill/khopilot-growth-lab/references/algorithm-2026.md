# Algorithm Mechanics (2024–2026)

Read when you need the *why* behind the rig, or when a user questions strategy. Tagged **[META]** (Mosseri / Meta newsroom / Transparency Center) vs **[CONSENSUS]** (reputable marketer analysis citing Meta). Exact percentages are mostly [CONSENSUS] — use them to prioritize, not to prove.

## How distribution actually works

There is no single "algorithm." Reels is ranked per surface (Reels-tab chaining, Explore, Feed recs) by **predict-then-rank**: pull ~100 candidate reels, predict user actions (watch-through, like, send, follow…), score, order. **[META]** Meta does not publish the weights.

The loop a creator optimizes against: a post is **seeded to a small test audience → early watch time + sends measured → reach expanded in waves if it performs.** **[META, 2024]** For a zero-follower account this is *the* engine: non-follower performance is literally the only thing measured, which is why post #1 can go viral.

## Ranking signals, by stated importance

**Top 3 — Mosseri, Jan 2025 [META]:** (1) **watch time**, (2) **likes per reach**, (3) **sends per reach** — with **sends per reach the most powerful for reaching new audiences.**

Other model inputs Meta lists (unordered): likelihood to watch >3s vs skip <2s (the hook gate), extended watch time, reshare, comment, "Interested" tap, use-audio, follow-after-watch. **[META]** Saves and completion rate are widely treated as important but are **not** in Mosseri's named top 3 **[CONSENSUS]**.

## What this means operationally

- **Watch time governs survival; sends per reach governs spread.** Win the seed test with retention, then break out with sends. **[META framing]**
- **Per-reach rates, not totals.** A small reel with a high send-rate beats a big reel with a low one. Follower count is not a gate. **[META]**
- **The <3s skip is a literal prediction model** → a strong mute hook mechanically lifts the watch-time prediction → more reach. **[META mechanism]**
- **Completion / loop-backs** lift "extended watch time"; a video that loops can read as >100% watched. Consistent with the model; exact thresholds are **[CONSENSUS]**.

## What gets suppressed [META]

Reposts/aggregators (rolling-30-day-window → non-recommendable platform-wide, 2026), third-party watermarks, >3 min reels, no-audio reels, accounts not in good standing, fact-check-flagged misinformation. AI-generated content requires a label (disclosure, not a confirmed reach penalty).

## Things people believe that are NOT reach levers

- **Hashtags do not increase reach.** [META, Mosseri 2025]
- **Trending/specific audio does not directly drive reach** — audio *presence* is an eligibility requirement; which audio is not a multiplier. [META, paraphrased] Treat trending audio as cultural-relevance nicety, not strategy.
- **"3–5× sends vs likes", "40–60% original boost", "1.7s decision", "95% completion"** — all [CONSENSUS], no Meta primary. Directional only.

## Cold-start playbook for a new account

1. Win the **<3s mute hook** (beat the skip predictor).
2. Hold **watch-through/completion** (lift the #1 signal).
3. Engineer the **send moment** (the breakout lever).
4. Stay **eligible** (original, no watermark, audio, <3 min).
5. Optionally use **Trial Reels** to test on non-followers first.
6. Track **sends/reach** in Insights as the leading indicator of breakout.

## Primary sources

Meta Transparency Center (Reels Chaining / Explore / Feed Recommendations system cards) · Mosseri statements via Buffer, Hootsuite, Later, Sprout Social, Dataslayer · TechCrunch 2024-04-30 (original-creator update) · Tubefilter/PetaPixel 2026-04-30 (aggregator crackdown). Full URLs in the research note under `brain/experiments/` (Veo/algorithm research, 2026-06-29).
