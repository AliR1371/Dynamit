# Session 19 — Utilising Element Geometry and Location

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural

---

## Learning Objectives

- Extract geometric data from Revit elements: location points and bounding boxes
- Understand how Dynamo represents Revit geometry for spatial analysis
- Apply spatial reasoning to answer questions like 'is this element inside this room?'

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Element.Location` | Get the XY(Z) location point of an element |
| `Element.Geometry` | Get the full solid geometry of an element |
| `Element.BoundingBox` | Get the axis-aligned bounding box of an element |
| `BoundingBox.MinPoint` / `MaxPoint` | Get the corner points of a bounding box |
| `Geometry.DistanceTo` | Measure distance between two geometry objects |
| Point arithmetic | Average Min and Max to find centroid |

---

## Practical Example

**Place markers at room centroids**

1. `All Elements of Category` → Rooms
2. `Element.Geometry` → retrieve each room's solid geometry
3. `Element.BoundingBox` → get the bounding box of each room
4. Average the MinPoint and MaxPoint → calculate the centroid
5. `FamilyInstance.ByPoint` → place a marker family at each centroid
6. See markers appear at the centre of every room in the model

**Spatial containment check:**
Take a set of Mechanical Equipment. Get each equipment's `Element.Location` point. Check whether it falls within its expected room's bounding box. Output a list of equipment that appears to be outside any room — a critical QA check for FM handover.

This session prepares the conceptual foundation for the advanced clash detection and room-coordination sessions.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `19_Element_Geometry.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 18 — Parameter Data Transfer and Coordination](../18-parameter-data-transfer-and-coordination/) |
| ➡ Next | [Session 20 — Extending Dynamo with Packages and Custom Nodes](../20-extending-dynamo-with-packages/) |
