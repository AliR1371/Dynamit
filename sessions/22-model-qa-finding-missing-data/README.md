# Session 22 — Model QA — Finding Missing or Inconsistent Data

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Build Dynamo routines that automatically validate model data against defined rules
- Flag elements with null, blank, or out-of-range parameter values
- Produce a QA summary report and optionally mark failing elements with a flag parameter

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.GetParameterValueByName` | Read the parameter to validate |
| `== null` check | Detect null (missing) parameter values |
| `String.Length == 0` | Detect empty string values |
| `FilterByBoolMask` | Separate passing and failing elements |
| `Data.ExportExcel` | Export the QA report |
| `Element.SetParameterByName` (QA flag Yes/No) | Mark failing elements visually in Revit |

---

## Practical Example

**Room data validation**

Define three rules for Rooms:
- Name must not be empty
- Number must not be empty
- Area must be > 1 m² (catches unplaced or zero-area rooms)

1. Retrieve all Rooms
2. Check each rule → three boolean lists
3. Combine with AND logic → one pass/fail boolean per room
4. `FilterByBoolMask` → isolate failing rooms
5. Export: Room ID | Name | Number | Fail Reason
6. Write `"Yes"` to a `"QA_Fail"` Yes/No shared parameter on each failing room
7. Open a colour-coded Room Schedule — failing rooms are highlighted in red

**Second validation:**
Check all Sheets for empty `"Drawn By"` and `"Checked By"` fields before issue. Flag any sheet that is not fully signed off.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `22_Model_QA.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 21 — Clash Detection and Coordination Checks](../21-clash-detection-and-coordination-checks/) |
| ➡ Next | [Session 23 — Room/Space and Equipment Data Coordination](../23-room-space-and-equipment-data-coordination/) |
