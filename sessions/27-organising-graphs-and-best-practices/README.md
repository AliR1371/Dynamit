# Session 27 — Organising Graphs and Best Practices

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Organise a Dynamo graph into clearly labelled sections for team readability
- Apply colour-coded groups, canvas notes, and consistent node naming
- Optimise graph performance by disabling unnecessary previews and controlling run order

---

## Key Nodes & Concepts

| Tool / Concept | How to access | Purpose |
|---|---|---|
| Group tool | Select nodes → Ctrl+G | Create a labelled, colour-coded group |
| Canvas Notes | Double-click empty canvas | Add a text annotation to the workspace |
| Node renaming | F2 on a node | Give a node a meaningful name |
| Preview toggle | Right-click node → Preview | Disable geometry preview to improve performance |
| Run mode | Settings → Run | Switch between Automatic and Manual |

---

## Practical Example

**Refactor the Session 13 sheet-creation graph to professional standard**

1. **Create three groups:**
   - `INPUT — Excel file path and sheet index` (colour: green)
   - `PROCESS — duplicate check and data preparation` (colour: blue)
   - `OUTPUT — create sheets` (colour: orange)

2. **Add a Canvas Note at the top:**
   > *Purpose: Auto-create drawing sheets from Excel. Run in Manual mode. Ensure title block family is loaded before running.*

3. **Rename key nodes:**
   - File path node → `"Excel Sheet Index Path"`
   - Title block selector → `"Title Block Family"`

4. **Disable geometry preview** on all nodes (this graph has no geometry)

5. **Switch to Manual run mode**

The graph now looks professional, is self-documenting, and any team member can safely run it without opening a single node.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `27_Organised_Sheet_Creation.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 26 — Batch Placing Views on Sheets](../26-batch-placing-views-on-sheets/) |
| ➡ Next | [Session 28 — Dynamo Player and Script Deployment](../28-dynamo-player-and-script-deployment/) |
