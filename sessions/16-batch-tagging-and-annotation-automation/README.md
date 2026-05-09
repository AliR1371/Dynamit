# Session 16 — Batch Tagging and Annotation Automation

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Automatically place tags on all untagged elements in a view using Dynamo
- Control tag type, leader visibility, and target view programmatically
- Adapt the tagging script to any element category without rebuilding from scratch

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Tag.ByElement` / `Tag.ByElementAndView` | Place a tag on an element in a specified view |
| View selection (active or by name) | Target the correct view for tag placement |
| FamilyType selection (tag family) | Choose which tag family to use |
| `Element.Location` | Used to position the tag at the element's location |

---

## Practical Example

**Tag all Doors in the active view**

1. Get the active floor plan view
2. `All Elements of Category` → Doors (filtered to the active view)
3. `Tag.ByElementAndView` — tag family: Door Tag, `hasLeader = false`
4. Run — all doors receive tags instantly

Compare to Revit's built-in 'Tag All Not Tagged': Dynamo lets you filter which elements to tag, choose specific tag families, and exclude elements — the built-in command cannot do this.

To retarget to a different category:
- Change the category input to Pipes → tag all pipes in the view (MEP)
- Change category to Structural Columns → tag all columns (Structural)
- Change the tag family input to match

**Note:** batch tagging places tags at the element's location point. Some tags may overlap — minor manual fine-tuning of leader lines is still expected after running.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `16_Batch_Tagging.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 15 — Automated Renumbering Techniques](../15-automated-renumbering-techniques/) |
| ➡ Next | [Session 17 — Data Extraction for Model Auditing (QA/QC)](../17-data-extraction-for-model-auditing/) |
