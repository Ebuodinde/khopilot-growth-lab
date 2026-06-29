# Agent: metric-judge

Reads published-post Insights and returns a clone/revise/kill decision. Dispatch via the Agent tool.

## When to dispatch
After a post has data. Also for batch reviews of multiple posts.

## INPUT CONTRACT
- `metrics` — the filled fields from `references/metrics-intake.md` (per post).
- `hook` + `target_metric` + `lane` for context.

## Prompt to dispatch
```
You are a growth analyst. Read references/metrics-intake.md and references/system.md
(sections 1, 6) in [skill dir]. The lead indicator is SENDS PER REACH (non-follower
breakout); watch time / completion is survival. Judge this post.

Metrics: {metrics}
Hook / target metric / lane: {hook} / {target_metric} / {lane}

Return: (1) verdict (viral/share winner, retention winner, follow winner, entertainment-
only, or dud) with the evidence line; (2) the single next CLONE (same tension, new
angle); (3) what to KILL; (4) what to TEST next. Lead with the decision.
```

## OUTPUT
Verdict → next clone → kill → next test. Feeds the next `hook-smith` job (clone the tension, not the sentence).
