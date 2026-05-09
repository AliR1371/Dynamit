# Session 17 — Data Extraction for Model Auditing (QA/QC)

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Extract model data that standard Revit schedules cannot display (e.g. worksets)
- Identify and flag elements that fail project standards or have unexpected properties
- Export a structured audit report to Excel for review by the BIM team or project lead

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.GetParameterValueByName` (Workset) | Read the workset name of an element |
| `All Elements of Category` (multiple categories) | Retrieve elements across several categories |
| `FilterByBoolMask` | Separate passing and failing elements |
| `Data.ExportExcel` | Write the audit report to Excel |
| `String.Contains` (rule check) | Test whether a value matches expected text |

---

## Practical Example

**Workset compliance check**

1. Retrieve all elements across Walls, Floors, Roofs, Structural Framing
2. `Element.GetParameterValueByName` → `"Workset"` for each element
3. Define expected workset name per category (e.g. Walls should be on `"A-Shell"`)
4. Build a condition: `workset != expected` → boolean flag for each element
5. `FilterByBoolMask` → isolate non-compliant elements
6. `Data.ExportExcel` → export: Element ID | Category | Current Workset | Expected Workset

**Second validation:** check all views and flag any where the `"View Template"` parameter is empty — these views are not following office standards.

This QA check catches modelling errors before coordination meetings. A BIM manager can run it in 60 seconds before any issue or submission.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `17_Model_Audit_QA.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 16 — Batch Tagging and Annotation Automation](../16-batch-tagging-and-annotation-automation/) |
| ➡ Next | [Session 18 — Parameter Data Transfer and Coordination](../18-parameter-data-transfer-and-coordination/) |
