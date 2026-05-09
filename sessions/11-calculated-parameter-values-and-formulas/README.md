# Session 11 — Calculated Parameter Values and Formulas

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Perform calculations on element data and write the computed results back to parameters
- Use conditional logic to enforce design rules or thresholds across many elements
- Eliminate manual repetitive calculations and reduce human error on large models

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Math.Round` | Round to nearest integer |
| `Math.Floor` | Round down |
| `Math.Ceiling` | Round up |
| Code Block formula | Write multi-step calculations compactly |
| `Element.GetParameterValueByName` | Read source parameter |
| `Element.SetParameterByName` | Write calculated result |
| Conditional `? :` logic | Apply thresholds or category flags |

---

## Practical Example

**Calculate Occupant Load for all Rooms and write it back**

1. `All Elements of Category` → Rooms
2. `Element.GetParameterValueByName` → `"Area"` (Revit returns area in internal units — ft²)
3. Convert to m²: `area * 0.0929`
4. Apply occupancy formula: `Math.Floor(area_m2 / 4.6)` — produces an occupant count
5. `Element.SetParameterByName` → write result to custom instance parameter `"Occupant Load"`
6. Open a Room Schedule in Revit — all occupant loads are populated

Discipline extensions:
- MEP → `area * 10` → write to `"Design Airflow"` (L/s)
- Structural → `volume * density` → write to `"Calc Weight"`

**Key insight:** Dynamo replaces the spreadsheet calculator that someone would otherwise maintain manually and sync to Revit by hand.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `11_Calculated_Parameters.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 10 — Importing and Updating from Excel](../10-importing-and-updating-from-excel/) |
| ➡ Next | [Session 12 — Automating View Creation by Level](../12-automating-view-creation-by-level/) |
