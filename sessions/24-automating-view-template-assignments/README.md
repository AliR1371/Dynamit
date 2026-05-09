# Session 24 — Automating View Template Assignments

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Apply view templates to large sets of views in a single Dynamo run
- Filter views by type, name pattern, or other criteria before assigning templates
- Enforce visual standards firm-wide without manually opening every view

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `All Elements of Category: Views` | Get all views in the model |
| `Element.Name` (filter by string) | Filter to views matching a name pattern |
| View Template retrieval by name | Get the template element and its ElementId |
| `Element.SetParameterByName` (View Template parameter) | Assign the template to matching views |

---

## Practical Example

**Apply 'Production — Plan' template to all ARCH- floor plan views**

1. Retrieve all views in the model
2. Filter to keep only `FloorPlan` view type (read the `ViewType` parameter)
3. Further filter to views whose names start with `"ARCH-"`
4. Find the view template named `"Production — Plan"` — view templates appear as view elements in Dynamo
5. Get its `ElementId`
6. `Element.SetParameterByName` → parameter: `"View Template"`, value: the template's ID
7. Verify in View Properties — templates are applied across all filtered views

Second pass:
- All views starting with `"ELEC-"` → get template `"Production — Electrical"`

**A project with 200 views can be fully templated in under 30 seconds.**

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `24_View_Template_Assignment.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 23 — Room/Space and Equipment Data Coordination](../23-room-space-and-equipment-data-coordination/) |
| ➡ Next | [Session 25 — Working with Linked Models in Dynamo](../25-working-with-linked-models/) |
