# Quickstart: Personal Site

**Branch**: `001-personal-site` | **Date**: 2025-02-20

## Prerequisites

- A text editor.
- A modern browser (desktop or mobile) for viewing.
- No build tools, Node, or npm required.

## Repository Layout

```text
index.html       # Main page (biography, projects, social/GitHub links)
css/style.css    # Styles and responsive layout
js/main.js       # Optional enhancements (core content works without it)
```

## Run Locally

1. Clone or open the repository.
2. Open `index.html` in a browser (e.g. double-click, or `file:///path/to/repo/index.html`).
   - Or serve the repo root with any static server (e.g. `python -m http.server 8000`, then visit `http://localhost:8000`).
3. Verify:
   - Biography section is visible and readable.
   - Projects list is visible; project links (if any) work.
   - Social and GitHub links are visible and go to the correct URLs.
4. Test without JavaScript: disable JS in the browser and reload; content and links should still work.
5. Test responsive: resize the window or use device emulation; layout should adapt, no horizontal scroll for main content.

## Editing Content

- **Biography**: Edit the biography section in `index.html` (text and optional headings).
- **Projects**: Add or edit project entries in the projects section of `index.html` (title, optional description, optional `<a href="...">`).
- **Social / GitHub links**: Update the link area in `index.html` with correct labels and `href` values.

## Deployment

- Deploy the repository root (or a folder containing `index.html`, `css/`, and optionally `js/`) to any static host or CDN (e.g. GitHub Pages, Netlify, S3, Azure Static Web Apps). No server-side configuration required beyond serving static files.

## Reference

- **Spec**: [spec.md](./spec.md)  
- **Plan**: [plan.md](./plan.md)  
- **Content structure**: [contracts/content-structure.md](./contracts/content-structure.md)  
- **Data model**: [data-model.md](./data-model.md)
