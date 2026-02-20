# Contract: Content Structure (Personal Site)

**Branch**: `001-personal-site` | **Date**: 2025-02-20

This contract defines the required structure and semantics of the single-page personal site. There are no HTTP APIs; the “contract” is the document structure and content blocks that the page MUST provide.

---

## Document Structure

The delivered page MUST include the following content areas, in any order that preserves a logical reading flow (e.g. biography first, then projects, then links):

1. **Biography**
   - At least one section dedicated to the professional biography.
   - Content MUST be visible without login and without requiring JavaScript to render.
   - SHOULD use semantic structure (e.g. `<section>`, headings, paragraphs) for accessibility and clarity.

2. **Projects**
   - A list (or equivalent) of projects.
   - Each project MUST have at least a title/name visible to the user.
   - Each project MAY have an optional description and an optional external link.
   - If a project has a link, the link MUST point to the correct external resource.

3. **Social and GitHub links**
   - At least one link to GitHub (label and URL).
   - One or more links to social media profiles (as provided by the site owner).
   - Links MUST be identifiable (e.g. by label or accessible name) and MUST navigate to the correct URL when activated.

---

## Link Behavior

- External links (projects, social, GitHub) MAY open in the same tab or in a new tab/window.
- The site MUST remain reachable after following a link (e.g. via back button or new-tab behavior).

---

## Responsive and Non-JS Requirements

- The page MUST be usable on common mobile and desktop viewport sizes (FR-005, SC-003).
- Primary content (biography, project list, social/GitHub links) MUST be available and links MUST work without JavaScript (FR-006, SC-004).

---

## Verification

- **Structure**: Manual or automated check that the three content areas exist and are present in the DOM.
- **Links**: Each external `href` checked for correctness (destination URL matches intent).
- **No-JS**: Load page with JavaScript disabled; verify content visible and links clickable.
- **Responsive**: Test at representative viewport widths (e.g. 320px, 768px, 1280px); no horizontal scroll or cut-off primary sections.
