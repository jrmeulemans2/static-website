# Data Model: Personal Site

**Branch**: `001-personal-site` | **Date**: 2025-02-20

Content is authored in HTML; there is no database or runtime data store. This document describes the logical entities and their representation in the page.

---

## Biography

**Purpose**: The professional narrative for the site owner (who they are, background, focus).

| Attribute   | Description                    | Validation / Notes                          |
|------------|--------------------------------|---------------------------------------------|
| Content    | Text (and optional structure) | Visible without login or extra navigation   |
| Sections   | Optional (e.g. intro, experience) | Semantic headings for structure and a11y |

**Representation**: One primary section in the page (e.g. `<section id="bio">` or equivalent), containing heading(s) and paragraphs. No separate “record”; content is the markup.

**Relationships**: None. Standalone content block.

---

## Project

**Purpose**: A single portfolio entry (work sample) with name and optional description/link.

| Attribute    | Description              | Validation / Notes                          |
|-------------|--------------------------|---------------------------------------------|
| Title/Name  | Required                 | Each project MUST be identifiable (FR-002)  |
| Description | Optional short summary   | Plain text or short paragraph               |
| URL         | Optional link            | If present, MUST resolve correctly (FR-004) |

**Representation**: List items or cards in a “Projects” section. Each entry has at least a title; optional description and `<a href="...">` when a URL is provided.

**Relationships**: None. List is unordered from a data perspective; order is presentation choice.

---

## Link (Social / GitHub)

**Purpose**: A labeled link to an external profile (GitHub or social platform).

| Attribute | Description     | Validation / Notes                          |
|----------|------------------|---------------------------------------------|
| Label    | Visible text     | E.g. "GitHub", "LinkedIn"                   |
| URL      | Destination      | MUST be correct and reachable (FR-003, FR-004) |

**Representation**: Anchor elements in a dedicated area (e.g. footer or “Links” section). At least one GitHub link and one or more social links as provided by the owner.

**Relationships**: None. Independent links; no hierarchy required.

---

## State and Validation

- **No runtime state**: All content is static in HTML. No persistence layer or API.
- **Link validation**: Manual or tool-based check that each `href` matches intended destination.
- **Responsiveness**: No state transitions; layout is determined by CSS and viewport.
