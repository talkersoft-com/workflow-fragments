## Plan overview

Before listing files or next steps, write a short paragraph (2–4 sentences) that summarises
what this plan will accomplish in plain language. It should cover: the problem being solved,
the approach taken, and what the system looks like when the work is done.

Example shape (fill in from the actual plan):

> This plan removes the dead deck-level `.mcp.json` write from `Apply()` and replaces the
> boolean `force_overwrite` field with a three-value `mode` string so operators can choose
> overwrite, skip, or merge behaviour per config. Backwards compatibility is preserved via
> a shim that promotes old configs on load. When complete, `hv mcp` writes only the
> workspace root file, and `claude_settings.mode` is the canonical control point.

Keep it under 80 words. No headers, no bullet points — just prose.
