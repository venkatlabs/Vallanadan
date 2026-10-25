# Vallanadan — Author Website

Static author website maintained in this repository. The current entry point is `index.html`; cover artwork is stored in `images/`. The `manuscripts/earlier-works/` folder contains a separate historical README.

## Current repository layout (audited 2026-10-25)

| Path | Verified size / purpose |
| --- | --- |
| `index.html` | 3,985,038 bytes (large standalone HTML page; historical review identified embedded base64 covers) |
| `covers.js` | 648,201 bytes; reported unused in the historical handoff, **not independently verified** |
| `images/` | Eight JPEG book-cover files (about 0.87–1.26 MB each) and `author.jpg` |
| `README.md` | Previously empty |
| `AGENTS.md`, `HANDOFF.md` | Absent on main at audit time |

## Performance and accessibility improvement plan

1. **Inspect the full HTML source before editing.** The GitHub connector currently returns an empty body for the 3.99 MB `index.html`, despite reporting its blob SHA. Use an authorized local clone or other reliable source reader; verify that it matches main before changing references.
2. **Extract inline cover artwork safely.** Identify all embedded `data:image/` sources and their corresponding book labels. Convert to individually named, visually checked WebP assets. Keep originals until review confirms that all references work. Use meaningful `alt` text, explicit dimensions and lazy loading where appropriate.
3. **Measure instead of assuming.** Record before/after HTML bytes, transferred image bytes, request count and page-load behavior; aim for HTML below 1.5 MB without sacrificing legibility. A target of about 100 KB per WebP cover is a starting hypothesis, not a verified output.
4. **Remove `covers.js` only after proving it is unreferenced.** Search all HTML and scripts; propose removal in a reviewable PR, not directly on main.
5. **Add page metadata and share previews.** Provide a unique descriptive `<title>`, description, canonical URL when the live domain is confirmed, Open Graph title/description/image, viewport, and sensible image alternatives. Do not invent a public site URL.
6. **Validate before merge.** Open the static page locally and inspect all covers, manuscript links, keyboard navigation and mobile layout. Confirm that private Drive manuscript links remain private. No deploy or production change is authorized by this documentation-only PR.

## Working conventions

- Changes are proposed through a branch and reviewed pull request; do not push directly to `main`.
- Keep private Drive manuscript URLs and personal credentials out of new documentation.
- The authoritative cross-agent checkpoint is `HANDOFF.md` on the work branch, with the linked Notion AI Action Inbox card for decisions and ownership.
- This repository currently has no `package.json` or CI/test harness in the root; do not claim automated tests passed without running them.

## Current status

This README is documentation only. The HTML, cover images, `covers.js`, live site, and deployment have **not** been changed or tested by the 2026-10-25 audit.
