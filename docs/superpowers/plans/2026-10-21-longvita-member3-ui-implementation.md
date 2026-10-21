# Longvita Member 3 UI Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Do not use Claude or Codex. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Hoàn thiện toàn bộ phần Member 3 của Longvita: 10 wireframe, 10 Final UI, state variants, responsive/accessibility QA, 3 prototype flows và PNG exports.

**Architecture:** Figma là nguồn thiết kế chính. Page 04 và Page 05 được chỉnh trước để thiết lập radius/contrast/component behavior; Page 02 và Page 03 chỉ dùng instances/tokens từ nền tảng này; Page 06 lắp lại các Final UI frames thành ba luồng prototype. Repo GitHub lưu spec, design rules, PNG exports và worklog/evidence, không chứa bản sao giả của Figma.

**Tech Stack:** Figma Design, Figma Auto Layout, Figma Variables/Styles, Figma Components/Variants, Prototype interactions, Figma MCP/use_figma, Git, Markdown, PNG exports.

**Spec:** `docs/superpowers/specs/2026-10-21-longvita-member3-ui-design.md`

## Global Constraints

- Không sử dụng Claude hoặc Codex; ChatGPT tự thực hiện.
- Không dùng emoji trong UI hoặc tài liệu Member 3.
- Master mobile size: `360x800`; kiểm tra responsive ở `412dp` bằng Auto Layout/Fill container, không scale giả.
- Radius scale: `4 / 8 / 12 / 16 / full`; không dùng 28/32/44 làm default card radius.
- Normal text contrast `>= 4.5:1`; large text/graphical controls `>= 3:1`.
- Touch target `>= 48x48dp`; body text `>= 14sp`, nội dung chính ưu tiên `16sp`.
- Không biểu đạt trạng thái chỉ bằng màu; phải có icon hoặc text label.
- Giữ nghiệp vụ trong `ux/user-flow.md`; không thêm feature ngoài rubric.
- Reuse Page 05 component instances; không detach nếu không thật sự cần.
- Không chỉnh sửa Task 4/handoff ngoài cập nhật nhỏ cần thiết để phản ánh output Member 3.

## Review Focus

1. Nội dung dài hoặc viewport 412dp không được gây overflow/truncate nội dung quan trọng — kiểm tra trong Task 8.
2. Primary button, border/control và supporting text phải đạt contrast — kiểm tra trong Task 1 và Task 8.
3. Day selector, icon button, checkbox và row action phải có hitbox tối thiểu 48dp — kiểm tra trong Task 1 và Task 8.
4. Error/recovery state phải giữ dữ liệu gốc và có đường thoát hợp lệ — kiểm tra trong Task 7 và Task 9.
5. Prototype phải không có dead-end, Back sai đích hoặc overlay biến thành màn hình mới — kiểm tra trong Task 9.

---
### Task 1: Normalize Design Tokens and Component Geometry

**Files / Figma targets:**
- Modify: `design/DESIGN.md`
- Modify: `design/design-decisions.md`
- Modify Figma: Page `1:4` — `04 Design System`
- Modify Figma: Page `1:5` — `05 Components`
- Verify component groups: Button `55:111`, TextField `55:143`, Card `56:80`, Navigation `56:174`, AppBar `56:191`, Dialog `57:169`, Loading `57:181`, Empty `57:212`, Error `57:255`.

**Interfaces:**
- Consumes: approved radius/contrast rules from the spec and current Page 04/05 foundations.
- Produces: reusable token/component foundation for every later wireframe/final screen.

- [ ] **Step 1: Verify write access with one reversible Figma metadata-safe edit**

Change a temporary description/name suffix on Page 04, read it back, then restore it. Expected: authenticated Editor account can write and read the same file.

- [ ] **Step 2: Update repo design tokens**

Replace legacy `16/28/44` default radius guidance with `4/8/12/16/full`; document `#476429` as primary high-contrast action green and `#74796C` as functional control border.

- [ ] **Step 3: Update Page 04 specimens and usage rules**

Rename radius specimens to `radius/4`, `radius/8`, `radius/12`, `radius/16`, `radius/full`; explicitly state that full/pill is limited to chips and segmented selection.

- [ ] **Step 4: Update Page 05 master geometry**

Set standard Button/Card/TextField/list containers to restrained radii: controls 8–12, standard cards 12, large dialog 16. Preserve 48dp hitboxes and existing component variant structure.

- [ ] **Step 5: Verify foundation**

Inspect Page 04/05 metadata and screenshots. Expected: no standard card/button master uses 28/32/44 radius; primary action pair passes 4.5:1 for normal label text; icon/day/checkbox interactive containers remain >=48dp.

- [ ] **Step 6: Commit repo documentation sync**

```bash
git add design/DESIGN.md design/design-decisions.md
git commit -m "design: normalize Longvita mobile tokens"
```

### Task 2: Build Flow 1 Wireframes

**Figma target:** Page `1:2` — `02 Wireframe`

**Interfaces:**
- Consumes: updated Page 04/05 structure and `ux/user-flow.md` Flow 1.
- Produces: grayscale `360x800` frames `S01 Home`, `S02 Food Preferences`, `S03 Create Meal Plan`, `S04 Weekly Meal Plan`, `S10 Saved Plans`.

- [ ] **Step 1: Create a Flow 1 section and five named 360x800 frames**

Use a consistent 16dp page margin, Auto Layout sections, grayscale fills, no food photography, no decorative blobs.

- [ ] **Step 2: Wireframe S01 and S02**

S01 hierarchy: greeting → one summary → primary Create Weekly Plan CTA → low-priority modules. S02: Age, Weight, Meals/day, Eating Window grouped with persistent labels and clear editable/calculated distinction.

- [ ] **Step 3: Wireframe S03, S04 and S10**

S03: Essential → Optional nutrition → Review & Generate. S04: day selector → meals → Save → Ingredients/Shopping route. S10: saved plan list plus empty-state location.

- [ ] **Step 4: Verify Flow 1 wireframes**

Count exactly five independent frames; confirm each has primary task hierarchy and no visual styling beyond grayscale structure. Expected: all frames are 360x800 and named exactly as specified.
### Task 3: Build Flow 2 Wireframes

**Figma target:** Page `1:2` — `02 Wireframe`

**Interfaces:**
- Consumes: Task 1 foundation and Flow 2 rules from `ux/user-flow.md`.
- Produces: grayscale frames `S07 Ingredient Summary` and `S08 Shopping List`, plus reserved locations for overlay/empty/snackbar states.

- [ ] **Step 1: Create two named 360x800 frames under a Flow 2 section**

S07 must expose category grouping, quantity/edit affordance and Create Shopping List CTA. S08 must expose category grouping and large checkbox rows suitable for one-handed use.

- [ ] **Step 2: Reserve S07 state zones**

Place clearly labeled wireframe references beside S07 for Edit Ingredient Dialog, Validation Error, Empty Ingredients and Undo Snackbar; these are state variants, not additional screens.

- [ ] **Step 3: Verify Flow 2 wireframes**

Expected: exactly two independent screens, checkbox/action hitbox layouts can accommodate 48dp, and the route `S04 → S07 → S08` is visually obvious from labels/actions.

### Task 4: Build Flow 3 Wireframes

**Figma target:** Page `1:2` — `02 Wireframe`

**Interfaces:**
- Consumes: Task 1 foundation and Flow 3 rules from `ux/user-flow.md`.
- Produces: grayscale frames `S05 Recipe Details`, `S06 Meal Alternatives`, `S09 Book Knowledge`.

- [ ] **Step 1: Create three named 360x800 frames under a Flow 3 section**

Keep the same 16dp mobile margin and Auto Layout structure used by Tasks 2–3.

- [ ] **Step 2: Wireframe S05**

Order: hero/media block -> recipe name -> provenance -> serving/protein -> ingredients -> numbered steps -> Replace Meal. Avoid card-per-step treatment.

- [ ] **Step 3: Wireframe S06 and S09**

S06: alternatives with reason/source/action plus reserved No Alternatives and Update Error zones. S09: concise principles, source/citation block and restrained knowledge sections.

- [ ] **Step 4: Verify all Page 02 wireframes**

Programmatically count named S01–S10 frames. Expected: exactly 10 independent 360x800 screens, all grayscale, no duplicate ID, and state variants not counted as screens.

### Task 5: Build Flow 1 Final UI from Stitch Remix

**Figma target:** Page `1:3` — `03 Final UI`

**Interfaces:**
- Consumes: Tasks 1–2, Stitch v2/v3 assets, Page 05 component instances.
- Produces: polished master frames `S01 Home`, `S02 Food Preferences`, `S03 Create Meal Plan`, `S04 Weekly Meal Plan`, `S10 Saved Plans` at 360x800.

- [ ] **Step 1: Create Flow 1 section and master frames**

Use `#F6F1E7` canvas, restrained surface cards, primary `#476429`, text tokens and current typography direction. Use component instances for navigation, app bars, buttons, cards, fields and badges.

- [ ] **Step 2: Remix S01 and S02**

Preserve Stitch's organic warmth but reduce dashboard/card density. S01 must prioritize Create Weekly Plan. S02 must scan as a real mobile form rather than a collection of oversized pills.

- [ ] **Step 3: Remix S03 and S04**

Keep the useful v2 three-part S03 information architecture. S04 must reduce long-feed density, retain a clear day selector, one consistent meal-card language, Save action and visible path to ingredients/shopping.

- [ ] **Step 4: Design S10**

Use moderate-density saved plan rows/cards, dates and essential metadata only; include clear empty-state placement and Create Plan recovery CTA.

- [ ] **Step 5: Verify Flow 1 visual consistency**

Expected: no pill-everywhere appearance, standard cards use <=16 radius, hierarchy is readable at 360dp, and all normal-size text/action labels meet contrast rules.
### Task 6: Build Flow 2 Final UI

**Figma target:** Page `1:3` — `03 Final UI`

**Interfaces:**
- Consumes: Tasks 1 and 3 plus Page 05 CheckboxRow, Dialog, Snackbar, Button and AppBar components.
- Produces: polished `S07 Ingredient Summary` and `S08 Shopping List` masters at 360x800.

- [ ] **Step 1: Design S07 Ingredient Summary**

Group by ingredient category with clear quantity/unit, edit affordance and Create Shopping List CTA. Prefer dividers/spacing over wrapping every row in a card.

- [ ] **Step 2: Design S08 Shopping List**

Use category headers and 48dp minimum checkbox rows. Purchased status must remain understandable without color through check icon/text treatment.

- [ ] **Step 3: Verify one-handed interaction geometry**

Inspect checkbox rows, edit actions, category controls and bottom CTA. Expected: every actionable target is >=48dp and no row becomes cramped at 360dp.

### Task 7: Build Flow 3 Final UI and Required States

**Figma target:** Page `1:3` — `03 Final UI`

**Interfaces:**
- Consumes: Tasks 1 and 4 plus Page 05 Badge, Card, Dialog, Empty and Error components.
- Produces: polished `S05 Recipe Details`, `S06 Meal Alternatives`, `S09 Book Knowledge` plus all state variants required across S03/S04/S06/S07.

- [ ] **Step 1: Design S05 Recipe Details**

Use strong recipe title/media hierarchy, source provenance, serving/protein summary, ingredients and numbered steps. Replace Meal must remain discoverable without competing with cooking content.

- [ ] **Step 2: Design S06 Meal Alternatives**

Each option shows meal name, short substitution rationale, source badge and Select action. Preserve the original meal context so cancel/error never implies the replacement succeeded.

- [ ] **Step 3: Design S09 Book Knowledge**

Use concise principle sections and citation/source treatment; avoid a long article layout and avoid decorative cards where a heading/divider is enough.

- [ ] **Step 4: Create required state variants beside parent screens**

Create exact names: `S03 / Loading`, `S03 / Generation Error`, `S04 / Save Error`, `S06 / No Alternatives`, `S06 / Update Error`, `S07 / Empty Ingredients`, `S07 / Edit Ingredient Dialog`, `S07 / Dialog Validation Error`, `S07 / Undo Snackbar`.

- [ ] **Step 5: Verify state semantics**

Expected: Generation Error offers Retry/Edit Preferences/Cancel; Save Error preserves generated plan; Update Error preserves original meal; Dialog Validation Error keeps the dialog open; Empty states expose a useful next action; snackbar has an Undo action.

### Task 8: Responsive and Accessibility QA

**Files / Figma targets:**
- Create: `docs/member-3-ui-worklog.md`
- Inspect: Page `1:3` — all Final UI frames and state variants
- Inspect: Page `1:5` — component masters

**Interfaces:**
- Consumes: Tasks 1 and 5–7.
- Produces: verified 360dp/412dp layouts and written evidence for rubric/demo.

- [ ] **Step 1: Create 412dp QA copies or responsive specimens**

Resize through Auto Layout/Fill container, never uniform scale. Verify wrapping, full-width cards/rows and CTA sizing.

- [ ] **Step 2: Run overflow and long-content checks**

Test the longest visible meal names, explanatory copy and category labels. Expected: no important text clipped; horizontal scroll is absent unless intentionally designed.

- [ ] **Step 3: Run contrast checks**

Verify normal text >=4.5:1 and large text/control boundaries >=3:1. Record tested foreground/background pairs in `docs/member-3-ui-worklog.md`.

- [ ] **Step 4: Run target-size and type checks**

Programmatically inspect interactive frames/components where possible. Expected: icon buttons, day selectors, checkbox rows and actions >=48x48dp; body labels >=14sp.

- [ ] **Step 5: Run non-color-cue check**

Review selected, purchased, logged, pending, warning and error states in grayscale. Expected: icon/text conveys every state even when hue is ignored.

- [ ] **Step 6: Capture QA evidence**

Record frame names, tested widths, contrast results, touch-target results and any fixes made in the worklog.

- [ ] **Step 7: Commit QA evidence**

```bash
git add docs/member-3-ui-worklog.md
git commit -m "docs: record member 3 UI QA evidence"
```
### Task 9: Assemble and Verify the Interactive Prototype

**Figma target:** Page `1:6` — `06 Prototype`

**Interfaces:**
- Consumes: verified Final UI and state frames from Tasks 5–8.
- Produces: three runnable Flow Starting Points with working Back, overlay, retry/recovery and loading-to-result interactions.

- [ ] **Step 1: Place prototype instances/copies in three labeled flow sections**

Use the Final UI masters as the visual source. Do not redesign screens on Page 06.

- [ ] **Step 2: Connect Flow 1**

Connect `S01 → S02 when needed → S03 → S03 / Loading → S04 → Save → S10`. Connect Generation Error Retry to Loading, Edit Preferences to S02, Cancel to S01; connect Save Error Retry while preserving S04 content.

- [ ] **Step 3: Connect Flow 2**

Connect `S04 → S07 → S08`. Configure `S07 / Edit Ingredient Dialog` as an actual overlay, validation error as dialog-preserving recovery, remove action to Undo Snackbar, and empty state back to S04.

- [ ] **Step 4: Connect Flow 3**

Connect `S04 → S05 → S09 → S05 → S06 → S04`. No Alternatives must allow S02 or keep-original recovery; Update Error must Retry/Cancel without replacing the original meal.

- [ ] **Step 5: Verify all Back targets and no-dead-end behavior**

Walk every happy path and every required error branch from its Flow Starting Point. Expected: every displayed state has at least one valid continuation/back action and every Back returns to the logical previous screen.

- [ ] **Step 6: Verify special rubric interactions**

Expected: S07 edit appears as Overlay rather than a standalone navigation screen; S03 Loading transitions to S04 Result; three Flow Starting Points are visible and named.

### Task 10: Export Final Screens and Close Member 3 Evidence

**Files / Figma targets:**
- Create: `assets/figma/S01-home.png`
- Create: `assets/figma/S02-food-preferences.png`
- Create: `assets/figma/S03-create-meal-plan.png`
- Create: `assets/figma/S04-weekly-meal-plan.png`
- Create: `assets/figma/S05-recipe-details.png`
- Create: `assets/figma/S06-meal-alternatives.png`
- Create: `assets/figma/S07-ingredient-summary.png`
- Create: `assets/figma/S08-shopping-list.png`
- Create: `assets/figma/S09-book-knowledge.png`
- Create: `assets/figma/S10-saved-plans.png`
- Modify: `docs/member-3-ui-worklog.md`
- Optional sync only if evidence changed: `design/design-decisions.md`

**Interfaces:**
- Consumes: completed Tasks 1–9.
- Produces: submission-ready PNG evidence and final Member 3 completion record.

- [ ] **Step 1: Export exactly the ten master Final UI frames**

Export at normal Figma PNG scale unless rubric requires another size. State variants/overlays are not counted among these ten exports.

- [ ] **Step 2: Verify exported assets**

Expected: all ten files exist, are non-empty PNGs, correspond one-to-one with S01–S10 and contain no duplicate screen export under a different name.

- [ ] **Step 3: Perform final Figma structure check**

Expected: Page 02 contains exactly 10 independent wireframes; Page 03 contains exactly 10 master Final UI screens plus clearly named state variants; Page 06 contains three flow starting points; important layers do not retain generic names such as `Frame 123` or `Rectangle 45`.

- [ ] **Step 4: Update final worklog**

Record completed screens, state list, 360/412 checks, prototype paths, overlay/loading evidence, PNG paths and any known non-blocking limitation. Do not claim checks that were not actually performed.

- [ ] **Step 5: Check repository scope before commit**

Run:
```bash
git status --short
git diff -- design/DESIGN.md design/design-decisions.md docs/member-3-ui-worklog.md
```
Expected: only Member 3 design documentation/evidence and intended PNG exports are staged; no Task 4 or unrelated files are modified.

- [ ] **Step 6: Commit final Member 3 deliverables**

```bash
git add assets/figma docs/member-3-ui-worklog.md design/DESIGN.md design/design-decisions.md
git commit -m "design: complete member 3 final UI and prototype evidence"
```

- [ ] **Step 7: Final acceptance review**

Check every acceptance criterion from the spec against real Figma/file evidence. Expected: 10 wireframes, 10 Final UI screens, all required states, reduced rounding, 360/412 pass, contrast/touch-target pass, three complete prototype flows, S07 overlay, S03 Loading → S04 Result, no dead ends and 10 PNG exports.

## Execution Notes

- Execute sequentially because Task 1 changes the visual/component contract consumed by every later task.
- Tasks 2–4 can only be reviewed independently after Task 1; Tasks 5–7 depend on their matching wireframes.
- Do not duplicate expensive redesign work across pages: fix master components/tokens first, then let instances inherit.
- Save meaningful Figma version-history milestones after foundation, wireframes, Final UI and prototype when the Figma client permits it.
- Repository implementation should use a dedicated Member 3 branch/worktree at execution time before further repo edits; Figma changes remain in the shared design file.
