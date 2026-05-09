# Session 28 — Dynamo Player and Script Deployment

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Use Dynamo Player to run scripts without exposing the Dynamo graph editor to end users
- Configure Input nodes so Player presents them as a simple form interface
- Plan a deployment strategy for distributing Dynamo scripts across a project team

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| **Dynamo Player** | Revit → Manage tab → Dynamo Player |
| Input node naming convention | Group inputs with a group titled `"Input:"` — Player exposes these as form fields |
| `Integer Slider` / `Number Slider` | Number inputs in Player |
| `String Input` | Text field input in Player |
| `Bool Toggle` | Checkbox input in Player |
| File path (network drive) | Store scripts on a shared network folder for team access |

---

## Practical Example

**Make the Session 12 view-creation graph accessible to non-Dynamo users**

Add three input nodes to the view-creation graph:
1. `String` input — `"Prefix for view names"` (e.g. `"ARCH"`)
2. `Bool Toggle` — `"Also apply view template?"`
3. `String` input — `"View template name"`

Group all three with a group titled `"Input:"` — Player reads this naming convention automatically.

Open Dynamo Player in Revit (Manage → Dynamo Player):
- Navigate to the graph file
- Player shows **only the three input fields** — no nodes, no wires, no Dynamo editor
- A project architect who has never opened Dynamo fills in the fields → clicks ▶ → views are created

**Deployment strategy:**
- Store all production graphs in a shared network folder (e.g. `\\server\BIM\Dynamo Scripts\`)
- Create a project-specific folder per project
- Add a Canvas Note README inside each graph for usage instructions
- Document inputs and expected results in each session's `README.md` in this repository

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `28_Player_Ready_View_Creation.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 27 — Organising Graphs and Best Practices](../27-organising-graphs-and-best-practices/) |
| ➡ Next | [Session 29 — Placing Elements from External Data (Coordinates)](../29-placing-elements-from-external-data/) |
