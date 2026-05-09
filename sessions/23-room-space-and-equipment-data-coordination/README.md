# Session 23 — Room/Space and Equipment Data Coordination

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟩 MEP · 🟦 Architecture · 🟨 BIM Management

---

## Learning Objectives

- Match MEP equipment or furniture to the room or space they physically occupy
- Use spatial containment logic to automate the room-to-element relationship
- Transfer room name and number to contained elements for accurate scheduling

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `All Elements of Category: Rooms / Spaces` | Get all rooms or spaces |
| `Element.Location` (equipment point) | Get each equipment item's location point |
| `BoundingBox.Contains` | Test if a point falls inside a bounding box |
| `Element.SetParameterByName` (equipment ← room data) | Write room name/number to the equipment |

---

## Practical Example

**Link Mechanical Equipment to its Room**

1. Retrieve all Mechanical Equipment (get location points)
2. Retrieve all Rooms (get bounding boxes)
3. For each piece of equipment, test its location point against every room's bounding box using `BoundingBox.Contains`
4. Take the first matching room
5. Write the matching room's `"Number"` → equipment `"Room Number"` parameter
6. Write the matching room's `"Name"` → equipment `"Room Name"` parameter
7. Verify in a Mechanical Equipment Schedule — every item now shows its room

**Why this matters for FM handover:**
Asset registers, maintenance schedules, and space utilisation reports all depend on knowing which room each piece of equipment is in. This script keeps that data accurate without manual entry.

Extend to:
- Furniture → Rooms (Architecture)
- Sensors and detectors → Spaces (MEP / Fire)

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `23_Room_Equipment_Coordination.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 22 — Model QA — Finding Missing or Inconsistent Data](../22-model-qa-finding-missing-data/) |
| ➡ Next | [Session 24 — Automating View Template Assignments](../24-automating-view-template-assignments/) |
