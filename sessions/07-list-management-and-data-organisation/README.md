# Session 07 — List Management and Data Organisation

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Understand how Dynamo structures data into lists and nested lists
- Use essential list operations: count, flatten, get item by index, group by key
- Prepare data structures correctly for downstream tasks like export or parameter setting

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `List.Count` | Count items in a list |
| `List.Flatten` | Collapse a nested list into a flat list |
| `List.GetItemAtIndex` | Retrieve one item by its position (0-indexed) |
| `List.GroupByKey` | Group a list into sub-lists based on a key value |
| `@L1`, `@L2` | List level selectors — control which level of nesting an operation targets |

---

## Practical Example

**Group Rooms by Level, then flatten**

1. `All Elements of Category` → Rooms
2. `Element.GetParameterValueByName` → `"Level"` — this becomes the key
3. `List.GroupByKey` (elements, keys) → produces a nested list: one sub-list of rooms per level
4. Inspect the nested output in the Watch node — it's a list of lists
5. `List.Flatten` → collapses everything back to one flat list of all rooms
6. `List.GetItemAtIndex` with index `2` → retrieves the third room

**The critical lesson on list levels:**
If you try to set parameters on a nested list, Dynamo may fail or apply values at the wrong level. The fix is:
- Use `List.Flatten` to reduce nesting, or
- Change the list level input port (`@L1` vs `@L2`) on the downstream node

**Key insight:** most beginner frustration in Dynamo comes from list structure mismatches. Master this session and the rest of the course becomes much smoother.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `07_List_Management.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 06 — Setting and Modifying Element Parameters](../06-setting-and-modifying-element-parameters/) |
| ➡ Next | [Session 08 — Code Blocks and Formulas in Dynamo](../08-code-blocks-and-formulas/) |
