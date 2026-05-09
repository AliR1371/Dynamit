# Session 29 — Placing Elements from External Data (Coordinates)

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Drive the placement of Revit family instances using XYZ coordinate data from Excel
- Handle coordinate system considerations (project coordinates vs survey coordinates)
- Verify placed elements against source data for accuracy

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Data.ImportExcel` (X, Y, Level columns) | Read coordinate data from Excel |
| `Point.ByCoordinates` | Build a placement point from X, Y, Z values |
| `FamilyInstance.ByPoint` | Place a family instance at a given point |
| `FamilyInstance.ByCoordinates` (with Level) | Place a family instance on a specific level |
| Family Type selection | Select which family type to place |

---

## Practical Example

**Place 80 light fixtures from a surveyor's coordinate spreadsheet**

1. Prepare an Excel file: `X (mm)` | `Y (mm)` | `Level Name` | `Fixture Type`
2. `Data.ImportExcel` → import and separate each column into its own list
3. Convert X and Y to Dynamo internal units if needed (divide by 304.8 for internal feet, or pass mm directly depending on Dynamo version)
4. `Point.ByCoordinates` → build placement points
5. Retrieve the target Level element by name matching
6. Select the FamilyType (e.g. `"Downlight – Recessed 100mm"`)
7. `FamilyInstance.ByPoint` or `FamilyInstance.ByCoordinates` → place all 80 fixtures in one run
8. Switch to Revit — all fixtures appear at the correct positions on the correct levels
9. Verify: compare `List.Count` of placed elements to the Excel row count

Structural extension:
- Place pile caps at surveyed pile head coordinates from a site engineer's spreadsheet

**Coordinate systems:** Always confirm whether the Excel coordinates are in project north or true north. Apply a rotation transform if the two coordinate systems are offset.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `29_Place_Elements_From_Coordinates.dyn` |
| *(coming with the video)* | `29_fixture_coordinates_template.xlsx` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 28 — Dynamo Player and Script Deployment](../28-dynamo-player-and-script-deployment/) |
| ➡ Next | [Session 30 — Final Project — Integrated Workflow Capstone](../30-final-project-integrated-workflow-capstone/) |
