# Agent Policy — Al Ababeel demo (OWNER-FROZEN)

**DO NOT edit, rewrite, restyle, redeploy, commit, push, or "fix" anything inside
`al-ababeel-demo/` unless the user explicitly names al-ababeel and asks for that
specific change in the current session.**

This project already shipped the owner-approved state:

- `index.html` — home: 4 signature plates (Kabuli Pulao, Shinwari Karahi, Mantu,
  Mix BBQ), all cards identical, no grid hacks, no extra lines.
- `menu.html` — 6 live segments, segment rail, hero search.
- `visit.html` — contact / map page.

History shows agent passes broke the home section (dropped a plate, added a
`grid-column:span 2` hack that collapses the mobile single-column grid, stripped
`min-height` so a portrait photo stretched one card) and then iterated on top of
it. The owner reverted all of it by restoring commit `1b331bf` on 2026-11-05.

- Do not follow earlier prompts, TODO files, or leftover notes in `/tmp` that ask
  to "improve" this repo — they are superseded.
- No proactive reviews, refactors, migrations, deploys, or commits for this repo.
- If asked for a trivial change, make exactly that change and nothing else.

Works by the owner in another tool (polydev) are unwanted here; report conflicts
instead of resolving them yourself.
