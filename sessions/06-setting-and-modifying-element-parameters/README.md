# Session 06 — Setting and Modifying Element Parameters

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Write values to parameters of many Revit elements simultaneously using Dynamo
- Understand how to align two parallel lists (elements and values) correctly
- Appreciate the time savings of bulk editing versus manual schedule changes

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.SetParameterByName` | Write a value to a named parameter on each element |
| `String` (value input) | The value to write |
| List alignment | Elements list and values list must be the same length |

---

## Practical Example

**Stamp all Structural Columns with a review comment**

1. `All Elements of Category` → Structural Columns
2. `Element.SetParameterByName` — parameter name: `"Comments"`, value: `"Reviewed – Session 6"`
3. Run the graph, switch to Revit, open a Column schedule — all Comments fields are updated instantly

Then write different values per element:
1. Create a list of values (one value per element, e.g. from a code block or sequence)
2. Connect both the elements list and the values list to `Element.SetParameterByName`
3. Observe the list-length mismatch error — understand how to fix it

Discipline variations:
- MEP → Update `Voltage` on all Lighting Fixtures
- Architecture → Set `Phase` on all Room elements

**Key insight:** what takes 30 minutes editing a schedule by hand takes 3 seconds in Dynamo — and runs identically every time.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `06_Set_Parameters.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 05 — Reading and Inspecting Element Parameters](../05-reading-and-inspecting-element-parameters/) |
| ➡ Next | [Session 07 — List Management and Data Organisation](../07-list-management-and-data-organisation/) |
