# Session 12 — Automating View Creation by Level

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Generate new Revit views automatically using Dynamo without manual setup
- Use Level elements as the driving data source for systematic view creation
- Apply a view template to newly created views to enforce visual standards immediately

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `All Elements of Category: Levels` | Get all Level elements in the model |
| `Element.Name` | Filter out unwanted levels by name |
| `View.PlanByLevel` | Create one Floor Plan view per level |
| `Element.SetParameterByName` (View Template) | Assign a View Template by element ID |

---

## Practical Example

**Create one Floor Plan per Level and apply a View Template**

1. `All Elements of Category` → Levels
2. Filter out reference/temporary levels whose names contain `"REF"`
3. Feed remaining levels into `View.PlanByLevel` — one Floor Plan view is created per level
4. Retrieve the newly created views
5. `Element.SetParameterByName` → parameter: `"View Template"`, value: the template's ElementId
6. Verify in the Revit Project Browser — all Floor Plans appeared in one run

Changing the view type input creates:
- Reflected Ceiling Plans
- Structural Framing Plans
- MEP services plans

**Key insight:** one graph serves all disciplines — just change the view type input.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `12_Create_Views_By_Level.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 11 — Calculated Parameter Values and Formulas](../11-calculated-parameter-values-and-formulas/) |
| ➡ Next | [Session 13 — Automating Sheet Creation from Lists](../13-automating-sheet-creation-from-lists/) |
