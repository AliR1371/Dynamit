# Session 01 — Introduction to Dynamo for Revit

> **Duration:** 20 min · **Level:** 🟢 Beginner · **Status:** ✅ Available

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Understand what Dynamo is and how it extends Revit for automation
- Navigate the Dynamo UI: workspace, library, nodes, connectors, and run modes
- Run a simple graph and observe how it interacts with a live Revit model

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| `Integer Slider` | Input a whole number value |
| `Number` | Input a decimal number value |
| `String` | Input a text value |
| `Watch` | Display output — the most-used debugging tool in Dynamo |
| Canvas / Library panel | Where you place nodes and search for new ones |
| Run Mode: **Automatic** | Graph re-runs on every change |
| Run Mode: **Manual** | Graph runs only when you click Run — use this on large scripts |

---

## Practical Example

**Hello World — String Concatenation + Number Addition**

1. Place a `String` node and type `Project`
2. Place a second `String` node and type ` A`
3. Connect both to a `String.Concat` node (or use a Code Block: `"Project" + " A";`)
4. Connect the output to a `Watch` node — the result is `Project A`
5. Below that, place two `Number` nodes (e.g. `5` and `3`)
6. Connect both to a `Math.Add` node
7. Connect the output to a second `Watch` — the result is `8`

This demonstrates the fundamental concept: **data flows from left to right through wires.**

### Key Discussion Points
- **Automatic vs Manual run mode** — automatic re-runs on every change (fast for small graphs), manual is safer when your script modifies the Revit model
- **The workspace is live-linked to Revit** — changes in Dynamo reflect in the model immediately when a graph runs

---

## Watch the Video

[![Watch on YouTube](https://img.shields.io/badge/Watch%20on-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtu.be/4D4NkhaxP9U)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 00 — Introduction](../00-introduction/) |
| ➡ Next | [Session 02 — Dynamo Basics — Nodes & Data Types](../02-nodes-and-data-types/) |
