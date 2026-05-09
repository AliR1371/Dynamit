# Session 26 — Batch Placing Views on Sheets

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Automate viewport creation by placing views onto their target sheets via Dynamo
- Match views to sheets using a naming convention or an external Excel mapping
- Define consistent placement coordinates for viewports on the sheet

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Viewport.Create` | Place a view onto a sheet at a specified point |
| `All Elements of Category: Views + Sheets` | Get all views and all sheets |
| String matching (view name ↔ sheet name) | Match each view to its target sheet by extracting a shared identifier |
| `Point` (placement coordinate on sheet) | X, Y position of the viewport on the sheet |
| `Data.ImportExcel` (optional mapping) | For complex multi-viewport sheet layouts |

---

## Practical Example

**Place all Floor Plan views onto their matching sheets**

1. Retrieve all Floor Plan views named `"ARCH - Level X Plan"`
2. Retrieve all Sheets named `"Level X — Floor Plan"`
3. Extract the level number from each name using String operations → use as the matching key
4. For each matched pair, call `Viewport.Create` with the sheet, the view, and a placement point

Placement coordinates:
- Dynamo uses the sheet's bottom-left corner as origin
- For a centred viewport on an A1 sheet: `Point(420, 190)` mm

5. Run → open the sheets in Revit — every plan is placed

**Multi-viewport sheets:**
For detail sheets with multiple viewports at different positions, prepare an Excel file with columns: View Name | Sheet Number | X | Y. Import and drive placement per row.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `26_Batch_Place_Views_On_Sheets.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 25 — Working with Linked Models in Dynamo](../25-working-with-linked-models/) |
| ➡ Next | [Session 27 — Organising Graphs and Best Practices](../27-organising-graphs-and-best-practices/) |
