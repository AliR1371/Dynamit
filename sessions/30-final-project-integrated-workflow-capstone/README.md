# Session 30 — Final Project — Integrated Workflow Capstone

> **Duration:** 20 min · **Level:** 🔴 Advanced · **Status:** 🔜 Coming Soon

**Disciplines:** 🟦 Architecture · 🟩 MEP · 🟥 Structural · 🟨 BIM Management

---

## Learning Objectives

- Combine techniques from across the course into one coherent end-to-end workflow
- Plan a multi-step automation sequence and execute it methodically
- Reflect on the value delivered and identify which techniques apply to your own projects

---

## Key Nodes & Concepts

All prior session techniques combined:
- Excel I/O (Sessions 09, 10)
- Selection + filtering + parameter setting (Sessions 03–06)
- View and sheet creation (Sessions 12, 13)
- Viewport placement (Session 26)
- View template assignment (Session 24)
- QA export (Sessions 17, 22)

---

## Capstone Scenario: New Project Setup and QA Pipeline

**Goal:** Starting from a blank Revit project and an Excel project brief, produce a fully set up, QA-checked, sheet-ready model — in under 3 minutes.

### Step-by-Step Pipeline

| Step | Action | Session Reference |
|------|--------|-------------------|
| 1 | Read an Excel project setup file: level names, sheet index, room programme | Session 10 |
| 2 | Create Floor Plan views for each level | Session 12 |
| 3 | Apply view templates to all new views | Session 24 |
| 4 | Create all drawing sheets from the sheet index | Session 13 |
| 5 | Place plan views onto their sheets at a defined position | Session 26 |
| 6 | Write room programme data (names, departments, target areas) to Room parameters | Session 10 |
| 7 | Run a QA check — flag empty room parameters, export warnings to Excel | Session 22 |

### What You Get
- All Floor Plan views created and templated
- All drawing sheets created with the correct numbers and names
- Plan views placed on sheets, ready for scale/viewport adjustment
- Room programme populated in the model
- A QA report highlighting any data gaps before the first issue

**Full pipeline run time: under 3 minutes.** Manual equivalent: 3–4 hours.

---

## Discussion: Your Action Plan

At the end of this session, reflect:
- Which of the 6 pipeline steps applies directly to your next project?
- Which sessions would you combine differently for your discipline?
- What would your first production Dynamo script automate?

This question is the point of the whole course — not just learning the tools, but changing how you work.

---

## Script Files

| File | Description |
|---|---|
| *(coming with the video)* | `30_Capstone_New_Project_Setup.dyn` |
| *(coming with the video)* | `30_project_setup_template.xlsx` |

---

## Watch the Video

> 🔜 **Coming Soon** — Subscribe to be notified.

[![Subscribe on YouTube](https://img.shields.io/badge/Subscribe-YouTube-FF0000?style=for-the-badge&logo=youtube)](https://youtube.com)

---

## You Did It

Completing all 30 sessions means you can:
- Automate parameter reading, writing, and validation at scale
- Generate views, sheets, and viewports from data
- Build QA/QC pipelines that catch errors before coordination meetings
- Deploy scripts to teammates who have never opened Dynamo

**Star ⭐ this repository and share it with your team.**

---

## Navigation

| | |
|---|---|
| ⬅ Previous | [Session 29 — Placing Elements from External Data](../29-placing-elements-from-external-data/) |
| 🏠 Back to start | [Course Home](../../README.md) |
