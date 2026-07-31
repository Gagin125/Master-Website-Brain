# Technical Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| Page language changes but URL stays old | Refresh/share can reopen wrong language | Update URL query with `history.replaceState` |
| Visible Lithuanian text but `<html lang="en">` remains | Bad for screen readers and SEO | Update `document.documentElement.lang` on every language change |
| Heavy hero video loads late | Weak first impression on mobile | Compress video, preload carefully, add poster when possible |
| No root `index.html` for Vercel | Vercel deploy can show 404 | Ensure root entry file is `index.html` |
| Mobile nav reuses desktop links | Links squeeze and logo loses hierarchy | Use mobile-specific nav structure |
| GitHub push before checking scope | Risk of pushing accidental changes | Always check `git status --short` first |
| Forgetting to propagate language to internal links | Moving pages resets language | Append `?lang=currentLang` to internal links |
| Editing wrong file after rename | Changes do not appear live | Confirm actual deployed entry file |
| Encoding corruption in Lithuanian or currency text | Text appears broken | Use UTF-8 meta and avoid bad copy pipelines |

## Language Switching Rules

- Visible text, URL query, and `document.documentElement.lang` must match.
- Internal navigation should preserve the active language.
- Language animation should affect text only unless the user explicitly wants layout/image animation.
- Do not rebuild galleries or image sections just because the language changed.

## Deployment Rules

- Check the actual deployed root file before assuming Vercel behavior.
- Confirm that the live URL opens before telling the user it is finished.
- If a site is blank on Vercel, check:
  - root `index.html`
  - wrong folder deployed
  - missing assets
  - case-sensitive file paths
  - oversized media
  - console errors

## Media Performance Rules

- Compress hero video.
- Add a poster frame when possible.
- Use `preload="metadata"` or a carefully chosen preload strategy.
- Lazy-load below-fold images.
- Do not lazy-load critical above-fold visuals if it causes a blank first impression.
