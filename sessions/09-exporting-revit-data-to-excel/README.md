# Session 09 — Exporting Revit Data to Excel

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Connect Dynamo to Excel to export Revit element data for external analysis
- Format data into a proper 2D list structure (rows and columns) for spreadsheet output
- Understand practical use cases: QA reports, quantity take-offs, consultant deliverables

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Data.ExportExcel` | Write a 2D list to a specified Excel file and worksheet |
| `File Path` node | Specifies the path to the target Excel file |
| `List.Create` | Manually create a list from individual inputs |
| `List.Transpose` | Flip rows and columns (columns of data → rows for Excel) |
| Headers row construction | Build the first row as a list of strings |

---

## Practical Example

**Export all Sheets to Excel (Sheet Number, Sheet Name, Revision)**

1. `All Elements of Category` → Sheets
2. `Element.GetParameterValueByName` × 3 for `"Sheet Number"`, `"Sheet Name"`, `"Current Revision"`
3. Build a header row: `["Sheet Number", "Sheet Name", "Revision"]`
4. Combine header + data rows into a 2D list (each row is a sub-list of cell values)
5. `Data.ExportExcel` with file path, sheet name `"Sheet Index"`, and the 2D list
6. Open the Excel file live in class and verify

**Key rule:** `Data.ExportExcel` expects a **list of rows** where each row is a **list of cell values**. A flat list will produce a single-column result.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `09_Export_To_Excel.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 08 — Code Blocks and Formulas in Dynamo](../08-code-blocks-and-formulas/) |
| ➡ Next | [Session 10 — Importing and Updating from Excel](../10-importing-and-updating-from-excel/) |
