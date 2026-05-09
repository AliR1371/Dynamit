# Session 05 — Reading and Inspecting Element Parameters

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Extract both instance and type parameters from Revit elements
- Distinguish parameter data types: text, numbers, yes/no, and element references
- Review retrieved data in bulk and identify blank or unexpected values

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.Parameters` | Returns all available parameters on an element |
| `Element.GetParameterValueByName` | Read a specific named parameter value |
| `Watch` node | Display data — essential for exploring parameter names and values |
| List inspection tools | Scroll through lists in the Watch node to spot missing data |

---

## Practical Example

**Inspect all parameters on Mechanical Equipment**

1. `All Elements of Category` → Mechanical Equipment
2. `Element.Parameters` on the first element → see every parameter name available
3. `Element.GetParameterValueByName` with `"Comments"` → lists every equipment's Comments field
4. Look at the Watch output and immediately identify which elements have blank fields

Discipline variations:
- Architecture → Read `Room Number` parameter on Doors
- MEP → Read `Diameter` parameter on Pipes

**Key insight:** this bulk data view in Dynamo replaces scrolling through properties one element at a time. It is essentially a live, custom schedule.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `05_Read_Parameters.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 04 — Filtering Elements by Parameter Values](../04-filtering-elements-by-parameter-values/) |
| ➡ Next | [Session 06 — Setting and Modifying Element Parameters](../06-setting-and-modifying-element-parameters/) |
