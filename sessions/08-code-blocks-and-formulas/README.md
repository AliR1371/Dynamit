# Session 08 — Code Blocks and Formulas in Dynamo

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Write compact expressions in the Code Block node for math and string operations
- Replace multiple nodes with a single code block to keep graphs readable
- Implement simple conditional (if/then) logic using the ternary operator

---

## Key Nodes & Concepts

| Node / Concept | Syntax |
|---|---|
| Code Block (basic) | `x + y;` |
| Division | `height / 1000;` |
| String join | `prefix + " - " + number;` |
| Ternary (conditional) | `condition ? valueIfTrue : valueIfFalse;` |

---

## Practical Example

**Three code block upgrades**

1. **mm → m conversion:** `height / 1000;`
   Replaces a `Math.Divide` node + two `Number` nodes

2. **Room label:** `roomName + " - " + roomNum;`
   Replaces a `String.Concat` node + extra wiring

3. **Area flag:** `area > 50 ? "Large" : "Small";`
   Replaces an `If` node + two `String` nodes

Then refactor a portion of the Session 06 graph using code blocks — the canvas becomes noticeably cleaner and easier to read.

**Ground rule:** use code blocks when they improve clarity. Don't use them to show off or to hide logic that would be clearer as explicit nodes.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `08_Code_Blocks.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 07 — List Management and Data Organisation](../07-list-management-and-data-organisation/) |
| ➡ Next | [Session 09 — Exporting Revit Data to Excel](../09-exporting-revit-data-to-excel/) |
