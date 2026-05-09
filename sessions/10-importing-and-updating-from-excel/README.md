# Session 10 — Importing and Updating from Excel

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Read data from an Excel file into Dynamo and interpret it correctly
- Match imported rows to the correct Revit elements using a shared key field
- Update model parameters from external Excel input to close the data loop

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Data.ImportExcel` | Read an Excel file into a 2D list |
| Worksheet selection | Specify which tab to read from |
| `String.ToNumber` | Convert text to number where needed |
| `List.IndexOf` | Find the position of a matching value — used to align Excel rows to model elements |
| `Element.SetParameterByName` | Write the matched value back to Revit |

---

## Practical Example

**Rename Sheets from an Excel file**

1. Prepare an Excel file with two columns: `Sheet Number` and `New Sheet Name`
2. `Data.ImportExcel` — read the file, select the correct worksheet
3. Separate the two columns into parallel lists
4. `All Elements of Category` → Sheets — read current `Sheet Number` from each
5. `List.IndexOf` — for each Excel row's sheet number, find its position in the Revit sheet list
6. Use that index to get the matching Revit sheet element
7. `Element.SetParameterByName` → write the new name

**The round-trip workflow:**
Session 09 (export → Excel) → edit the Excel file → Session 10 (import → update model)

This is one of the most-used real-world Dynamo workflows across all disciplines.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `10_Import_From_Excel.dyn` |
| *(coming with the video)* | `10_sheet_rename_template.xlsx` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 09 — Exporting Revit Data to Excel](../09-exporting-revit-data-to-excel/) |
| ➡ Next | [Session 11 — Calculated Parameter Values and Formulas](../11-calculated-parameter-values-and-formulas/) |
