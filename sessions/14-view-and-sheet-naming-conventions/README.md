# Session 14 — View and Sheet Naming Conventions

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Bulk-rename views or sheets using Dynamo to enforce project naming standards
- Use string manipulation to add prefixes, suffixes, or perform find-and-replace on names
- Audit existing names for non-compliance and correct them programmatically

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `String.Concat` | Join strings together (add a prefix or suffix) |
| `String.Replace` | Find and replace text within a string |
| `String.Contains` | Check if a string contains a substring |
| `String.StartsWith` | Check if a string begins with a specific prefix |
| Code Block (string formatting) | Compact string operations |
| `Element.SetParameterByName` (Name / Sheet Number) | Write the corrected name back |

---

## Practical Example

**Enforce 'ARCH-' prefix on all Floor Plan views**

1. Retrieve all views of type `FloorPlan`
2. `String.StartsWith` → check which names do NOT start with `"ARCH-"`
3. `FilterByBoolMask` → isolate non-compliant views
4. `String.Concat` → prepend `"ARCH-"` to each non-compliant name
5. `Element.SetParameterByName` → write the corrected name back

Then demonstrate find-and-replace:
- Change all views containing `"Ground"` to `"Level 00"` using `String.Replace`
- Add a project code prefix to every sheet number

**Especially valuable** after receiving a model from a consultant whose naming conventions don't match yours — one Dynamo run normalises everything across hundreds of views.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `14_Naming_Conventions.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 13 — Automating Sheet Creation from Lists](../13-automating-sheet-creation-from-lists/) |
| ➡ Next | [Session 15 — Automated Renumbering Techniques](../15-automated-renumbering-techniques/) |
