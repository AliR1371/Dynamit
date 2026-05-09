# Session 02 — Dynamo Basics — Nodes & Data Types

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Recognise different node types: Revit-specific nodes vs generic core nodes
- Understand Dynamo data types: numbers, strings, booleans, and Revit element references
- Connect nodes to build basic relationships such as arithmetic or text operations

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Number` | Decimal number input |
| `String` | Text input |
| `Boolean` | True / False input |
| `Math.Add` | Adds two numbers |
| `String.Concat` | Joins two or more strings |
| `Boolean Toggle` | On/off switch — used later in filtering logic |

---

## Practical Example

**Distance calculation + Room code generation**

1. Add two `Number` nodes (e.g. 3500 and 1200) and connect them to `Math.Add` → Watch shows 4700
2. Join a room prefix with a number: `"ROOM-" + "101"` → Watch shows `ROOM-101`
3. Intentionally add a String to a Number without conversion — observe the type error and understand why data types matter
4. Introduce the `Boolean Toggle` node — true/false values will be used in Session 04 filtering

**Key insight:** every wire in Dynamo carries a specific data type. Connecting incompatible types produces an error — this is by design, not a flaw.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `02_Nodes_And_Data_Types.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified when this session is published.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://www.youtube.com/@RevitDynamics)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 01 — Introduction to Dynamo for Revit](../01-introduction-to-dynamo-for-revit/) |
| ➡ Next | [Session 03 — Selecting and Querying Revit Elements](../03-selecting-and-querying-revit-elements/) |
