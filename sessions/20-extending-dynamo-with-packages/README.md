# Session 20 — Extending Dynamo with Packages and Custom Nodes

> **Duration:** 20 min · **Level:** 🔵 Intermediate · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Discover and install community packages from the Dynamo Package Manager
- Use nodes from a popular package to simplify tasks built earlier in the course
- Create a simple custom node by encapsulating a reusable group of nodes

---

## Key Nodes & Concepts

| Node / Concept | Purpose |
|---|---|
| Package Manager UI (search, install, version) | Find and install community packages |
| **Clockwork** | Popular package for sheet/view management and Revit-specific utilities |
| **Rhythm** / **ArchiLab** | Packages that extend linked model access and other advanced features |
| Custom Node creation | Group → right-click → Create Custom Node |

---

## Practical Example

**Install Clockwork and create a custom node**

1. Open Package Manager → search for `"Clockwork"` → install
2. Locate the Clockwork `Sheet.ByNameNumberTitleBlock` node — compare it to the multi-step approach from Session 13
3. Preview an ArchiLab node that retrieves elements from a linked model (preview for Session 25)

**Create a 'RenumberByLocation' custom node:**
1. Take the renumbering logic from Session 15 (sort → sequence → set parameter)
2. Select all those nodes → Ctrl+G to group them
3. Right-click the group → **Create Custom Node**
4. Name it `RenumberByLocation`, add input and output port labels
5. Save it — it now appears in your local Dynamo library as a reusable node

**Key insight:** every complex workflow you've built can be packaged and shared with teammates who never need to see the internals — they just plug in inputs.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `20_Packages_And_Custom_Nodes.dyn` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 19 — Utilising Element Geometry and Location](../19-utilising-element-geometry-and-location/) |
| ➡ Next | [Session 21 — Clash Detection and Coordination Checks](../21-clash-detection-and-coordination-checks/) |
