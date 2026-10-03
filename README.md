# pam-paper

The academic / technical paper on **PAM (Project Agentic Management)** — the next generation of
Open Library's [ADA](https://mek.fyi/papers/ada).

This reuses the **same build infrastructure as the ADA paper**: a single, dependency-free,
academic-preprint-styled **static HTML page** (`index.html`) plus a shared stylesheet (`styles.css`).
There is no LaTeX, no pandoc, and no bib toolchain — references are authored inline as an ordered
list, exactly as in the ADA paper. The design (serif body, two-column journal layout, numbered
sections via CSS counters, booktabs tables, TOC sidebar, light/dark theme toggle) is carried over
verbatim in `styles.css`.

## Build / preview

It is static. Just open it, or serve the folder:

```bash
# open directly
open index.html

# or serve (so relative paths behave like the deployed site)
python3 -m http.server 8000   # then visit http://localhost:8000/
```

## Deploy (mek.fyi)

The ADA paper is served by the mek.fyi Flask site: its catch-all `Section` view renders
`base.html` wrapping `templates/papers/ada.html`, with the stylesheet at `/papers/ada/styles.css`.
To publish this paper the same way, the deployed layout is:

- `mek.fyi/mekarpeles/templates/papers/pam.html`  ← the contents of `index.html`
- `mek.fyi/mekarpeles/static/papers/pam/styles.css` (or wherever `/papers/pam/styles.css` resolves)

reachable at `https://mek.fyi/papers/pam`. (Deployment is out of scope for this repo; `index.html`
references `styles.css` relatively so it also works offline as a standalone file.)

## Status

**Working draft.** Abstract written; section outline in place with per-section "outline notes" marking
what each section will contain. The paper sharpens as PAM does. Tracked by epic
[mekarpeles/PAM#33](https://github.com/mekarpeles/PAM/issues/33).
