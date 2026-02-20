<!--
  Sync Impact Report
  Version: (none) → 1.0.0
  Change: Initial ratification; principles and sections filled from user input (static website, minimal dependencies, responsive).
  Modified principles: N/A (all new)
  Added sections: Core Principles (5), Technology & Delivery, Quality & Review, Governance
  Removed sections: None
  Templates: plan-template.md ✅ (Constitution Check gate unchanged); spec-template.md ✅ (no mandatory section changes); tasks-template.md ✅ (task types compatible); commands in .specify/templates/commands/*.md: N/A (path does not exist); .cursor/commands/*.md: not under .specify
  Follow-up TODOs: None
-->

# Static Website Constitution

## Core Principles

### I. Static-First

Delivery MUST be static: HTML, CSS, and optional minimal JavaScript as files. No server runtime or database is required to serve core content. Rationale: Enables cheap hosting, CDN caching, and predictable behavior across environments.

### II. Minimal Dependencies

Dependencies MUST be kept to a minimum. Every dependency MUST be justified; prefer platform APIs and vanilla patterns over frameworks. Rationale: Reduces supply-chain risk, build complexity, and bundle size while keeping the project maintainable.

### III. Responsive (Mobile & Desktop)

The site MUST work well on mobile and desktop. Layout and interaction MUST adapt to viewport and input (touch and pointer/keyboard). Breakpoints and accessibility considerations (e.g. tap targets, readable text) are required. Rationale: Users access the site from varied devices; responsive design is non-negotiable for reach and usability.

### IV. Performance & Payload

Load time and payload MUST be optimized. Prefer measurable targets (e.g. LCP, FID, total transfer) where applicable. Avoid unnecessary assets and render-blocking resources. Rationale: Fast, small pages improve UX and work better on slow or constrained networks.

### V. Simplicity (YAGNI)

Start simple; avoid adding features or abstractions until they are needed. Complexity MUST be justified against the current scope. Rationale: Keeps the codebase understandable and aligned with “minimal dependencies” and static delivery.

## Technology & Delivery

- **Output**: Static assets (HTML, CSS, JS as needed) suitable for any static host or CDN.
- **Stack**: No mandatory framework; choose the smallest set of tools that satisfy principles (e.g. vanilla HTML/CSS/JS or a minimal static generator).
- **Build**: Build steps MUST be minimal and reproducible; avoid unnecessary tooling.

## Quality & Review

- **Constitution Check**: Plans and specs MUST pass a gate that verifies alignment with these principles (e.g. static delivery, dependency count, responsive behavior, performance).
- **Reviews**: Changes SHOULD be checked for responsive behavior, dependency additions (justified), and performance impact.
- **Guidance**: Use README or project docs for day-to-day development and runbooks.

## Governance

- This constitution supersedes ad-hoc practices for this project; decisions that conflict with it MUST be amended or the constitution updated.
- Amendments require documentation, rationale, and version bump (semantic: MAJOR = incompatible principle removal/change, MINOR = new principle or material expansion, PATCH = clarifications/typos).
- Compliance: All plans and feature work MUST verify alignment with the Constitution Check; deviations MUST be documented and justified (e.g. in a Complexity Tracking table).

**Version**: 1.0.0 | **Ratified**: 2025-02-20 | **Last Amended**: 2025-02-20
