# Session 18 — Parameter Data Transfer and Coordination

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Copy parameter values from type parameters down to instance parameters automatically
- Synchronise data between related elements to maintain a single source of truth
- Understand list alignment when matching elements to their types

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.Type` | Get the family type of each instance element |
| `Element.GetParameterValueByName` (from type) | Read a parameter value from the type |
| `Element.SetParameterByName` (to instance) | Write the type value to the instance |
| List alignment | The element list and its type list must stay in the same order |

---

## Practical Example

**Propagate Fire Rating from Door types to Door instances**

Background: Some schedules and tags read instance parameters, not type parameters. Fire Rating is often a type parameter, but the instance needs it for certain schedules to work correctly.

1. `All Elements of Category` → Doors (instances)
2. `Element.Type` → get each door's family type
3. `Element.GetParameterValueByName` → read `"Fire Rating"` from each type
4. `Element.SetParameterByName` → write that value to the instance `"Fire Rating"` parameter
5. Open a Door Schedule — all instances now carry the correct rating

MEP extension:
- Push `"Manufacturer"` from equipment type → instance `"Manufacturer"` field for FM exports

**Why this matters:** facility management exports, tags on plans, and certain schedules only see instance parameters. This propagation script keeps everything aligned with one run.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `18_Parameter_Data_Transfer.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 17 — Data Extraction for Model Auditing (QA/QC)](../17-data-extraction-for-model-auditing/) |
| ➡ Next | [Session 19 — Utilising Element Geometry and Location](../19-utilising-element-geometry-and-location/) |
