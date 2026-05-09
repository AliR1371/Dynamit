# Session 15 — Automated Renumbering Techniques

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Renumber rooms, doors, or other elements in a logical spatial sequence via Dynamo
- Sort elements by location coordinates or level before assigning sequential numbers
- Apply custom numbering schemes (floor prefix + sequence) programmatically

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.Location` | Get the XY location point of an element |
| `List.SortByKey` | Sort a list of elements by a corresponding key value |
| `Sequence` node | Generate a sequential list of numbers with a start, amount, and step |
| Code Block (number formatting) | Format numbers with zero-padding or prefixes |
| `Element.SetParameterByName` (Room Number / Door Mark) | Write the new number back |

---

## Practical Example

**Renumber all Rooms spatially (Level prefix + sequence)**

1. `All Elements of Category` → Rooms
2. `Element.Location` → get each room's XY point
3. Sort by Y coordinate first (north-to-south), then X (west-to-east)
4. `List.GroupByKey` by Level → group rooms per floor
5. For each group, generate a `Sequence`: Level 1 → 101, 102, 103…; Level 2 → 201, 202, 203…
6. `Element.SetParameterByName` → write back to `"Room Number"`
7. Open a Room Schedule — no duplicates, logical spatial order, instant result

The same logic applies to:
- Door Mark (Architecture)
- Equipment Tag (MEP)
- Structural member marks (Structural)

**This task takes hours manually on a large model. In Dynamo: under one minute.**

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `15_Automated_Renumbering.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 14 — View and Sheet Naming Conventions](../14-view-and-sheet-naming-conventions/) |
| ➡ Next | [Session 16 — Batch Tagging and Annotation Automation](../16-batch-tagging-and-annotation-automation/) |
