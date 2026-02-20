# Tasks: Personal Site

**Input**: Design documents from `specs/001-personal-site/`  
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/

**Tests**: Not requested in the feature specification; no test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Static site (this project)**: `index.html`, `css/style.css`, `js/main.js` at repository root (per plan.md)

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [x] T001 Create project structure per plan: index.html at repo root, css/ directory, js/ directory
- [x] T002 Add minimal HTML5 document shell to index.html (doctype, html, head with charset and viewport, body)
- [x] T003 [P] Add base styles to css/style.css (e.g. box-sizing, root font size, baseline for responsive layout)

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core layout and semantics so all user story sections can be added and displayed correctly

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

- [x] T004 Add responsive layout baseline to css/style.css (fluid or breakpoint-based layout so FR-005/SC-003 can be met; no horizontal scroll for main content)
- [x] T005 Add semantic structure to index.html (main landmark, optional nav) and link css/style.css so content sections have a container and styles apply

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel

---

## Phase 3: User Story 1 - View Professional Biography (Priority: P1) 🎯 MVP

**Goal**: A visitor can read a professional biography section that is visible and readable without login or JavaScript.

**Independent Test**: Open the site and verify a clearly identifiable biography section is visible and readable; content conveys professional identity.

### Implementation for User Story 1

- [x] T006 [US1] Add biography section to index.html per data-model.md (e.g. section with id="bio", heading, paragraphs; semantic structure)
- [x] T007 [US1] Add biography section styles to css/style.css (readable typography, spacing, line length for biography content)

**Checkpoint**: User Story 1 is complete; biography is independently testable

---

## Phase 4: User Story 2 - View List of Projects (Priority: P2)

**Goal**: A visitor sees a list of projects with at least a title per project; optional description and external link; entries are clearly separated.

**Independent Test**: Open the site and verify a list of projects is visible with at least a title per project; project links (if any) go to the correct destination.

### Implementation for User Story 2

- [x] T008 [US2] Add projects section to index.html with list of projects (each project has at least a title; optional description and anchor with href per data-model.md)
- [x] T009 [US2] Add project list styles to css/style.css (clear separation between projects, optional link styling; responsive)

**Checkpoint**: User Stories 1 and 2 are both independently testable

---

## Phase 5: User Story 3 - Access Social and GitHub Links (Priority: P3)

**Goal**: A visitor can reach GitHub and social profiles via clear, identifiable links; activating a link goes to the correct URL; site remains reachable (e.g. back or new tab).

**Independent Test**: Open the site and verify at least one GitHub link and one or more social links are visible and identifiable; activating them goes to the correct profile/page.

### Implementation for User Story 3

- [x] T010 [US3] Add social and GitHub links section to index.html (at least one GitHub link, one or more social links; each with label and correct href; use target/rel as needed per contracts/content-structure.md)
- [x] T011 [US3] Add link section styles to css/style.css (identifiable labels, adequate touch/click targets; responsive)

**Checkpoint**: All user stories are independently functional

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Verification and final checks across all content

- [x] T012 Run quickstart.md validation: open index.html in browser, verify content and links work with JavaScript disabled, check at mobile and desktop viewport sizes (per specs/001-personal-site/quickstart.md)
- [x] T013 [P] Verify all external links in index.html have correct href and accessible names per specs/001-personal-site/contracts/content-structure.md

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3–5)**: All depend on Foundational completion; can be done sequentially (US1 → US2 → US3) or in parallel if staffed
- **Polish (Phase 6)**: Depends on all user story phases complete

### User Story Dependencies

- **User Story 1 (P1)**: Starts after Phase 2 - No dependencies on other stories
- **User Story 2 (P2)**: Starts after Phase 2 - Independently testable; shares index.html and css/style.css with US1
- **User Story 3 (P3)**: Starts after Phase 2 - Independently testable; shares same files

### Within Each User Story

- Add HTML structure first, then styles (CSS) for that section
- Core content and links must work without JavaScript (no JS tasks required for spec)

### Parallel Opportunities

- T003 [P] can run in parallel with T002 (different files: css/style.css vs index.html) after T001
- T012 and T013 can run in parallel (validation vs link review)
- After Foundational phase, US1, US2, US3 could be split across developers (each owns their section in index.html and corresponding CSS)

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup  
2. Complete Phase 2: Foundational  
3. Complete Phase 3: User Story 1 (Biography)  
4. **STOP and VALIDATE**: Open site, confirm biography is visible and readable without JS  
5. Deploy or demo if ready  

### Incremental Delivery

1. Setup + Foundational → base page and responsive baseline  
2. Add US1 (Biography) → test independently → MVP  
3. Add US2 (Projects) → test independently  
4. Add US3 (Social/GitHub links) → test independently  
5. Run Phase 6 (Polish)  

### Parallel Team Strategy

1. Complete Setup + Foundational together  
2. Then: Developer A – US1, Developer B – US2, Developer C – US3 (coordinate edits to index.html and css/style.css to avoid conflicts)  

---

## Notes

- [P] tasks = different files, no dependencies  
- [USn] label maps task to user story for traceability  
- Each user story is independently testable per spec  
- No JavaScript tasks required; js/main.js is optional for future enhancements  
- Commit after each task or logical group; stop at checkpoints to validate story independently  
