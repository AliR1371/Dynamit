# Session 03 — Selecting and Querying Revit Elements

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Select elements in Revit both manually (by picking) and automatically (by category)
- Retrieve large collections of elements — all walls, all ducts, all beams — in one node
- Extract basic information: element count, names, and type identifiers

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Select Model Element` | Manually pick one element in Revit |
| `Select Model Elements` | Manually pick multiple elements |
| `All Elements of Category` | Retrieve every element of a chosen category |
| `Categories` | Dropdown to choose a Revit category (Doors, Walls, Ducts…) |
| `Element.Name` | Get the name of an element |
| `Element.Id` | Get the unique ID of an element |
| `List.Count` | Count how many items are in a list |

---

## Practical Example

**Retrieve and count all Doors in the model**

1. Place a `Categories` node and choose **Doors**
2. Connect it to `All Elements of Category` — this returns every door in the model
3. Connect the output to `List.Count` — the Watch shows the total door count
4. Also use `Select Model Elements` to manually pick five walls and read `Element.Name`

Discipline variations — all use the same node pattern, just change the category:
- Architecture → Rooms
- MEP → Ducts
- Structural → Structural Framing

**Key insight:** one graph pattern works across every discipline by simply changing the `Categories` input.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `03_Select_And_Query.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 02 — Dynamo Basics — Nodes & Data Types](../02-nodes-and-data-types/) |
| ➡ Next | [Session 04 — Filtering Elements by Parameter Values](../04-filtering-elements-by-parameter-values/) |
