# Session 25 — Working with Linked Models in Dynamo

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Access and query elements from linked Revit models within a Dynamo graph
- Compare data between the host model and a linked model to detect discrepancies
- Use Excel as an intermediate bridge when direct cross-model parameter writing is not possible

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `RevitLinkInstance` (select link) | Reference a linked model in the graph |
| `Document.GetElements` (from link) | Query elements from the linked document |
| `Element.GetParameterValueByName` (linked elements) | Read parameters from linked model elements |
| List comparison nodes | Compare two parallel lists side by side |
| `Data.ExportExcel` (cross-model report) | Export discrepancy table |

---

## Practical Example

**Level coordination: Structural vs Architectural model**

In a structural model with the architectural model linked in:

1. Retrieve all Level elements from the host (structural) model
2. Retrieve all Level elements from the linked (architectural) document via `Document.GetElements`
3. Compare level names side by side — flag any level that exists in one model but not the other
4. Compare level elevations — flag any where they differ by more than 1 mm
5. `Data.ExportExcel` → export the discrepancy report for the coordination meeting

**Second example — MEP vs Architectural space/room alignment:**
1. Retrieve Room names from the linked architectural model
2. Retrieve Space names from the MEP host model
3. `List.SetDifference` → flag rooms without a matching space name
4. The MEP engineer knows exactly which spaces need updating before the next coordination issue

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `25_Linked_Models.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 24 — Automating View Template Assignments](../24-automating-view-template-assignments/) |
| ➡ Next | [Session 26 — Batch Placing Views on Sheets](../26-batch-placing-views-on-sheets/) |
