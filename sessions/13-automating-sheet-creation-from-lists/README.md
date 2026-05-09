# Session 13 — Automating Sheet Creation from Lists

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Create multiple Revit sheets automatically from a list imported from Excel
- Assign title blocks programmatically and set sheet numbers and names in bulk
- Prevent duplicate sheet creation by checking existing sheets before running

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Sheet.ByNameNumberTitleBlock` | Create a Revit sheet with a specified number, name, and title block |
| `Data.ImportExcel` | Read the sheet index from Excel |
| `All Elements of Category: Sheets` | Retrieve existing sheets for the duplicate check |
| `List.SetDifference` | Remove already-existing sheet numbers from the creation list |
| FamilyType selection | Select the target title block family by name |

---

## Practical Example

**Create 80 sheets from an Excel sheet index**

1. Prepare an Excel file with two columns: `Sheet Number`, `Sheet Name`
2. `Data.ImportExcel` → import the list
3. `All Elements of Category` → Sheets → read existing `Sheet Number` values
4. `List.SetDifference` → remove any sheet numbers that already exist in the model (safety check)
5. Select the title block FamilyType by name
6. `Sheet.ByNameNumberTitleBlock` → creates all missing sheets in one run

A project with 80 drawing sheets can be fully set up in under 10 seconds. BIM managers can prepare the Excel sheet index on day one and hand it to Dynamo — no manual sheet creation ever needed.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `13_Create_Sheets_From_List.dyn` |
| *(coming with the video)* | `13_sheet_index_template.xlsx` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 12 — Automating View Creation by Level](../12-automating-view-creation-by-level/) |
| ➡ Next | [Session 14 — View and Sheet Naming Conventions](../14-view-and-sheet-naming-conventions/) |
