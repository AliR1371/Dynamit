# Session 21 — Clash Detection and Coordination Checks

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Detect hard clashes between two categories of elements using bounding box intersection
- Generate a structured clash report listing conflicting element pairs
- Understand the limitations of bounding-box clash detection vs solid geometry intersection

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `All Elements of Category` (two sets) | Get two categories to test against each other |
| `Element.BoundingBox` | Get each element's bounding box |
| `BoundingBox.Intersects` | Test if two bounding boxes overlap — returns true/false |
| `List.AllIndicesOf` | Find all positions of a value in a list |
| `Data.ExportExcel` (clash report) | Export the clash pairs table |

---

## Practical Example

**Duct vs Structural Framing clash check**

1. Retrieve all Ducts AND all Structural Framing elements
2. Generate a bounding box for each element in both lists
3. Nested `List.Map` + `BoundingBox.Intersects` → produces an N×M matrix of true/false
4. Extract pairs where the result is `true`
5. Compile a clash table: Duct ID | Beam ID | Duct Name | Beam Name
6. `Data.ExportExcel` → export the report
7. Open the Excel file — use Revit's 'Select by ID' tool to jump directly to each clash

**Limitations to understand:**
- Bounding boxes are axis-aligned — diagonal members and curved geometry produce false positives
- For accuracy on complex geometry, refine with solid intersection tests (covered as an extension)

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `21_Clash_Detection.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 20 — Extending Dynamo with Packages and Custom Nodes](../20-extending-dynamo-with-packages/) |
| ➡ Next | [Session 22 — Model QA — Finding Missing or Inconsistent Data](../22-model-qa-finding-missing-data/) |
