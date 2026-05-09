# Session 04 — Filtering Elements by Parameter Values

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Filter a collection of elements based on a parameter value condition
- Understand boolean masks: how a list of true/false values filters a parallel list of elements
- Combine category selection with filtering to isolate a precise subset of elements

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.GetParameterValueByName` | Read a named parameter from each element |
| `FilterByBoolMask` | Splits a list into matching (in) and non-matching (out) items |
| `==` (equality node) | Compares two values — returns true or false |
| `>` / `<` comparisons | Greater-than / less-than — for numeric conditions |
| `Code Block` (condition expression) | Write conditions compactly |

---

## Practical Example

**Filter walls by Fire Rating**

1. `All Elements of Category` → Walls
2. `Element.GetParameterValueByName` → parameter name: `"Fire Rating"`
3. `==` node comparing each value to `"2 Hour"` → produces a list of true/false (a boolean mask)
4. Feed both the original element list AND the boolean mask into `FilterByBoolMask`
5. The `in` output port returns only the walls rated "2 Hour"

Discipline variations:
- Architecture → filter Doors where Width > 900 mm
- MEP → filter Ducts on a specific system
- Structural → filter Beams with a particular material

**Key insight:** this pattern — get parameter → compare → filter — is the foundation of every QA/QC check you will build later in the course.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `04_Filter_By_Parameter.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 03 — Selecting and Querying Revit Elements](../03-selecting-and-querying-revit-elements/) |
| ➡ Next | [Session 05 — Reading and Inspecting Element Parameters](../05-reading-and-inspecting-element-parameters/) |
