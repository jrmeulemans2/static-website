# Research: Personal Site (001-personal-site)

**Branch**: `001-personal-site` | **Date**: 2025-02-20

## Stack: Vanilla HTML, CSS, JavaScript (No External Libraries)

**Decision**: Use only platform HTML, CSS, and JavaScript. No npm, no CDN libraries, no frameworks.

**Rationale**: User requirement and constitution (Minimal Dependencies, Simplicity). Reduces supply-chain risk, keeps payload minimal, and ensures the site works everywhere without build tooling. Aligns with FR-006 and SC-004 (core content and links available without JavaScript).

**Alternatives considered**:
- Static site generators (Eleventy, Hugo, etc.): Rejected—introduce dependencies and build step; not required for a single page.
- CSS frameworks (Bootstrap, Tailwind): Rejected—external dependency; custom CSS is sufficient for one page.
- JS frameworks (React, Vue): Rejected—no need for component state or SPA behavior; would violate no-external-libraries and add payload.

---

## Responsive Design Approach

**Decision**: Use fluid layout and CSS media queries for breakpoints. Mobile-first base styles; enhance for larger viewports. Ensure touch targets and readable text (e.g. minimum font size, line length).

**Rationale**: Constitution III (Responsive) and FR-005, SC-003. Single CSS file keeps dependency count zero and avoids render-blocking extra requests.

**Alternatives considered**:
- Separate mobile/desktop HTML: Rejected—duplication and maintenance burden; one responsive page is simpler.
- JavaScript-based layout: Rejected—violates no-JS baseline; CSS-only responsive is sufficient.

---

## JavaScript Role

**Decision**: JavaScript is optional. Use only for non-essential enhancements (e.g. smooth scroll, optional UI polish). All primary content (biography, projects, links) must be present in HTML and work with CSS only; links must work without JS.

**Rationale**: Spec FR-006 and SC-004 require primary content and link use without JavaScript. Keeping JS minimal supports Performance & Payload and avoids reliance on script for core behavior.

**Alternatives considered**:
- No JavaScript at all: Acceptable; current decision allows optional enhancements while preserving no-JS baseline.
- JS for content injection: Rejected—content must be in HTML so it works without JS.

---

## Content Authoring and “Contracts”

**Decision**: Content (biography, projects, social/GitHub links) is authored directly in HTML. Structure is documented in data-model.md and contracts/ as content structure and semantics (sections, headings, link targets), not as runtime APIs.

**Rationale**: Static-first; no backend or API. “Contracts” for this feature define the required document structure and content blocks so implementation and verification are clear.

**Alternatives considered**:
- Separate data file (JSON/YAML) plus JS to render: Rejected—adds JS dependency for content and conflicts with no-JS requirement.
- CMS or backend: Rejected—out of scope; spec assumes content maintained outside app (e.g. file edits).

---

## Performance and Payload

**Decision**: Single HTML file, one CSS file, optional single JS file. No images required by spec; if added later, use appropriate formats and dimensions. Avoid render-blocking scripts for above-the-fold content; defer or omit non-essential JS.

**Rationale**: Constitution IV (Performance & Payload). Minimal resources keep load time and transfer size low and support SC-001 (content visible within one minute).

**Alternatives considered**:
- Multiple CSS/JS bundles: Rejected—unnecessary for one page; would add complexity.
- Inline critical CSS: Optional later optimization; not required for initial scope.
