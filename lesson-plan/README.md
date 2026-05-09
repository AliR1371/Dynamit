# Dynamo for Revit — Complete Lesson Plan

> 30 Sessions · 10 Hours · Beginner to Advanced  
> Architecture · MEP · Structural · BIM Management

Each session is **20 minutes** and includes learning objectives, key nodes & concepts, and a practical classroom example.

---

## Beginner Level · Sessions 01–08

### Session 01 — Introduction to Dynamo for Revit

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Understand what Dynamo is and how it extends Revit for automation
- Navigate the Dynamo UI: workspace, library, nodes, connectors, and run modes
- Run a simple graph and observe how it interacts with a live Revit model

**Key Nodes & Concepts**
`Integer Slider` · `Number` · `String` · `Watch` · `Canvas / Library panel` · `Run modes (Auto / Manual)`

**Practical Example**
Build a 'Hello World' graph by concatenating two text strings (e.g. `'Project' + ' A'`) and outputting the result in a Watch node. Then add two number nodes and display the sum. Discuss the difference between Automatic and Manual run modes. Open Dynamo against a sample Revit model so students can see the workspace is live-linked.

---

### Session 02 — Dynamo Basics — Nodes & Data Types

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Recognise different node types: Revit-specific vs generic core nodes
- Understand Dynamo data types: numbers, strings, booleans, and Revit element references
- Connect nodes to build basic relationships such as arithmetic or text operations

**Key Nodes & Concepts**
`Number` · `String` · `Boolean` · `Math.Add` · `String.Concat` · `Boolean Toggle`

**Practical Example**
Construct a calculation graph adding two distances (3500 mm + 1200 mm). Join a room prefix string with a number to form `'ROOM-101'`. Demonstrate a type-mismatch error (adding a String to a Number) to teach why data types matter. Introduce the Boolean Toggle node.

---

### Session 03 — Selecting and Querying Revit Elements

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Select elements in Revit both manually (by picking) and automatically (by category)
- Retrieve large collections of elements — all walls, all ducts, all beams — in one node
- Extract basic information: element count, names, and type identifiers

**Key Nodes & Concepts**
`Select Model Element` · `Select Model Elements` · `All Elements of Category` · `Categories` · `Element.Name` · `Element.Id` · `List.Count`

**Practical Example**
Use the Categories dropdown to select 'Doors', connect to `All Elements of Category`, and feed the result into `List.Count`. Use `Select Model Elements` to manually pick walls and read `Element.Name`. Repeat for discipline-specific categories: Ducts (MEP), Structural Framing (Structural), Rooms (Architecture).

---

### Session 04 — Filtering Elements by Parameter Values

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Filter a collection of elements based on a parameter value condition
- Understand boolean masks: how a list of true/false values filters a parallel list of elements
- Combine category selection with filtering to isolate a precise subset of elements

**Key Nodes & Concepts**
`Element.GetParameterValueByName` · `FilterByBoolMask` · `==` (equality node) · `> / <` comparisons · `Code Block` (condition expression)

**Practical Example**
Retrieve all Walls. Read the 'Fire Rating' parameter with `Element.GetParameterValueByName`. Use `==` to compare to '2 Hour', producing a boolean list. Feed into `FilterByBoolMask`. Extend to other disciplines: filter doors by width > 900 mm, ducts by system, beams by material.

---

### Session 05 — Reading and Inspecting Element Parameters

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Extract both instance and type parameters from Revit elements
- Distinguish parameter data types: text, numbers, yes/no, and element references
- Review retrieved data in bulk and identify blank or unexpected values

**Key Nodes & Concepts**
`Element.Parameters` · `Element.GetParameterValueByName` · `Watch node` · List inspection tools

**Practical Example**
Select all Mechanical Equipment. Use `Element.Parameters` on one element to explore every available parameter. Then use `Element.GetParameterValueByName` with 'Comments' to list every equipment's Comments field in the Watch node — immediately showing which elements have blank fields.

---

### Session 06 — Setting and Modifying Element Parameters

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Write values to parameters of many Revit elements simultaneously using Dynamo
- Understand how to align two parallel lists (elements and values) correctly
- Appreciate the time savings of bulk editing versus manual schedule changes

**Key Nodes & Concepts**
`Element.SetParameterByName` · `String` (value input) · List alignment concepts

**Practical Example**
Select all Structural Columns. Use `Element.SetParameterByName` with parameter name 'Comments' and value 'Reviewed – Session 6' to stamp every column at once. Switch to Revit and show the updated values live in a Column schedule. Demonstrate writing different values (one per element) and the list-length mismatch error.

---

### Session 07 — List Management and Data Organisation

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Understand how Dynamo structures data into lists and nested lists
- Use essential list operations: count, flatten, get item by index, group by key
- Prepare data structures correctly for downstream tasks like export or parameter setting

**Key Nodes & Concepts**
`List.Count` · `List.Flatten` · `List.GetItemAtIndex` · `List.GroupByKey` · List levels (`@L1`, `@L2`)

**Practical Example**
Retrieve all Rooms and group them by Level using `List.GroupByKey`. Show the nested output in Watch (a list of lists). Use `List.Flatten` to collapse to one flat list. Demonstrate `List.GetItemAtIndex` to pull out a specific item. Discuss list levels and how nested lists cause errors in parameter-setting workflows.

---

### Session 08 — Code Blocks and Formulas in Dynamo

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Write compact expressions in the Code Block node for math and string operations
- Replace multiple nodes with a single code block to keep graphs readable
- Implement simple conditional (if/then) logic using the ternary operator

**Key Nodes & Concepts**
`Code Block` (x + y; syntax) · Math operations · String concatenation · Ternary: `condition ? valueIfTrue : valueIfFalse`

**Practical Example**
Convert a wall height from mm to metres: `height / 1000;`. Combine room name and number: `roomName + " - " + roomNum;`. Add a conditional flag: `area > 50 ? "Large" : "Small";`. Rewrite a portion of the Session 06 graph using code blocks and observe how the canvas simplifies.

---

## Intermediate Level · Sessions 09–20

### Session 09 — Exporting Revit Data to Excel

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Connect Dynamo to Excel to export Revit element data for external analysis
- Format data into a proper 2D list structure (rows and columns) for spreadsheet output
- Understand practical use cases: QA reports, quantity take-offs, consultant deliverables

**Key Nodes & Concepts**
`Data.ExportExcel` · `File Path node` · 2D list preparation (`List.Create`, `Transpose`) · Headers row construction

**Practical Example**
Build a graph that collects all Sheets and exports three columns — Sheet Number, Sheet Name, Revision — to Excel. Construct a header row, combine with data rows into a 2D list, and run the export live. Extend: export Room areas/names (Architecture), equipment with locations (MEP), beam sizes and levels (Structural).

---

### Session 10 — Importing and Updating from Excel

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Read data from an Excel file into Dynamo and interpret it correctly
- Match imported rows to the correct Revit elements using a shared key field
- Update model parameters from external Excel input to close the data loop

**Key Nodes & Concepts**
`Data.ImportExcel` · Worksheet selection · `String.ToNumber` (type conversion) · `List.IndexOf` (key matching) · `Element.SetParameterByName`

**Practical Example**
Prepare an Excel file with Sheet Number and New Sheet Name columns. Import with `Data.ImportExcel`, separate into parallel lists. Get all Sheets, read Sheet Number, use `List.IndexOf` to match, and write new names with `Element.SetParameterByName`. The Session 9 export → Excel edit → Session 10 import round-trip is the most-used real-world Dynamo workflow.

---

### Session 11 — Calculated Parameter Values and Formulas

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Perform calculations on element data and write the computed results back to parameters
- Use conditional logic to enforce design rules or thresholds across many elements
- Eliminate manual repetitive calculations and reduce human error on large models

**Key Nodes & Concepts**
`Math.Round` · `Math.Floor / Ceiling` · Code Block formula · `Element.GetParameterValueByName` · `Element.SetParameterByName` · Conditional `? :` logic

**Practical Example**
Retrieve all Rooms. Read 'Area' and convert to m²: `area * 0.0929`. Apply occupancy formula: `Math.Floor(area_m2 / 4.6)`. Write result to a custom 'Occupant Load' instance parameter. Show in a Room Schedule. MEP: compute `area * 10 L/s` for 'Design Airflow'. Structural: `volume * density` for 'Calc Weight'.

---

### Session 12 — Automating View Creation by Level

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Generate new Revit views automatically using Dynamo without manual setup
- Use Level elements as the driving data source for systematic view creation
- Apply a view template to newly created views to enforce visual standards immediately

**Key Nodes & Concepts**
`All Elements of Category: Levels` · `Element.Name` · `View.PlanByLevel` (or package equivalent) · `Element.SetParameterByName` (View Template)

**Practical Example**
Retrieve all Level elements, filter out reference levels (e.g. names containing 'REF'), feed remaining levels into `View.PlanByLevel` to create one Floor Plan per level. After creation, assign a View Template by element ID. Verify in the Project Browser. Discuss how changing the view type input creates Reflected Ceiling or Structural Framing Plans.

---

### Session 13 — Automating Sheet Creation from Lists

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Create multiple Revit sheets automatically from a list imported from Excel
- Assign title blocks programmatically and set sheet numbers and names in bulk
- Prevent duplicate sheet creation by checking existing sheets before running

**Key Nodes & Concepts**
`Sheet.ByNameNumberTitleBlock` · `Data.ImportExcel` · `All Elements of Category: Sheets` · `List.SetDifference` (duplicate check) · FamilyType selection

**Practical Example**
Prepare an Excel file with Sheet Number and Sheet Name columns. Import, retrieve existing sheet numbers, use `List.SetDifference` to remove duplicates, select a title block FamilyType, and feed into `Sheet.ByNameNumberTitleBlock`. A project with 80 sheets can be set up in under 10 seconds.

---

### Session 14 — View and Sheet Naming Conventions

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Bulk-rename views or sheets using Dynamo to enforce project naming standards
- Use string manipulation to add prefixes, suffixes, or perform find-and-replace on names
- Audit existing names for non-compliance and correct them programmatically

**Key Nodes & Concepts**
`String.Concat` · `String.Replace` · `String.Contains` · `String.StartsWith` · Code Block (string formatting) · `Element.SetParameterByName` (Name / Sheet Number)

**Practical Example**
Retrieve all FloorPlan views. Check which do not start with 'ARCH-'. Prepend 'ARCH-' to non-compliant views using `String.Concat`. Demonstrate find-and-replace: change all views containing 'Ground' to 'Level 00'. Apply the same prefix pattern to sheet numbers.

---

### Session 15 — Automated Renumbering Techniques

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Renumber rooms, doors, or other elements in a logical spatial sequence via Dynamo
- Sort elements by location coordinates or level before assigning sequential numbers
- Apply custom numbering schemes (floor prefix + sequence) programmatically

**Key Nodes & Concepts**
`Element.Location` · `List.SortByKey` · `Sequence node` · Code Block (number formatting) · `Element.SetParameterByName` (Room Number / Door Mark)

**Practical Example**
Retrieve all Rooms. Use `Element.Location` to get XY points. Sort by Y then X. Group by level, generate a Sequence for each group: Level 1 → 101, 102, 103…; Level 2 → 201, 202, 203…. Write back to 'Room Number'. Verify in a Room Schedule — no duplicates, logical order. A task that takes hours manually runs in under one minute.

---

### Session 16 — Batch Tagging and Annotation Automation

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Automatically place tags on all untagged elements in a view using Dynamo
- Control tag type, leader visibility, and target view programmatically
- Adapt the tagging script to any element category without rebuilding from scratch

**Key Nodes & Concepts**
`Tag.ByElement` / `Tag.ByElementAndView` · View selection (active or by name) · FamilyType selection (tag family) · `Element.Location` (for tag position)

**Practical Example**
Select the active floor plan view. Retrieve all Door elements visible in that view. Use `Tag.ByElementAndView` with a Door Tag family and `hasLeader = false`. Watch all doors receive tags instantly. Show how changing the category and tag family inputs tags Pipes (MEP) or Structural Columns (Structural) with no other changes.

---

### Session 17 — Data Extraction for Model Auditing (QA/QC)

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Extract model data that standard Revit schedules cannot display (e.g. worksets)
- Identify and flag elements that fail project standards or have unexpected properties
- Export a structured audit report to Excel for review by the BIM team or project lead

**Key Nodes & Concepts**
`Element.GetParameterValueByName` (Workset) · `All Elements of Type` (multiple categories) · `FilterByBoolMask` · `Data.ExportExcel` · `String.Contains` (rule check)

**Practical Example**
Build a workset compliance check across Walls, Floors, Roofs, Structural Framing. Define expected workset names per category (e.g. Walls should be on 'A-Shell'). Flag any element whose workset doesn't match. Export a report: Element ID | Workset | Expected Workset. Also flag all views where 'View Template' is empty.

---

### Session 18 — Parameter Data Transfer and Coordination

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Copy parameter values from type parameters down to instance parameters automatically
- Synchronise data between related elements to maintain a single source of truth
- Understand list alignment when matching elements to their types

**Key Nodes & Concepts**
`Element.Type` · `Element.GetParameterValueByName` (from type) · `Element.SetParameterByName` (to instance) · List alignment

**Practical Example**
All Door types have a 'Fire Rating' type parameter. Retrieve all Door instances. Use `Element.Type` to get each door's type. Read 'Fire Rating' from the type. Write it to the corresponding instance parameter. Verify in a Door Schedule. MEP: push 'Manufacturer' from equipment type to instance for FM exports.

---

### Session 19 — Utilising Element Geometry and Location

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Extract geometric data from Revit elements: location points and bounding boxes
- Understand how Dynamo represents Revit geometry for spatial analysis
- Apply spatial reasoning to answer questions like 'is this element inside this room?'

**Key Nodes & Concepts**
`Element.Location` · `Element.Geometry` · `Element.BoundingBox` · `BoundingBox.MinPoint / MaxPoint` · `Geometry.DistanceTo` · Point arithmetic

**Practical Example**
Get all Rooms and retrieve each room's solid geometry. Calculate the centroid of each room's bounding box. Use `FamilyInstance.ByPoint` to place a marker family at each centroid. Then check whether Mechanical Equipment location points fall within their expected room's bounding box.

---

### Session 20 — Extending Dynamo with Packages and Custom Nodes

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Discover and install community packages from the Dynamo Package Manager
- Use nodes from a popular package to simplify tasks built earlier in the course
- Create a simple custom node by encapsulating a reusable group of nodes

**Key Nodes & Concepts**
Package Manager UI (search, install, version) · Clockwork · Rhythm / ArchiLab · Custom Node creation (group → right-click → Create Custom Node)

**Practical Example**
Install the 'Clockwork' package and compare its `Sheet.ByNameNumberTitleBlock` to the Session 13 approach. Show an ArchiLab node retrieving elements from a linked model (preview for Session 25). Take the Session 15 renumbering logic, group it, right-click → Create Custom Node named 'RenumberByLocation', and save it as a reusable node.

---

## Advanced Level · Sessions 21–30

### Session 21 — Clash Detection and Coordination Checks

**Disciplines:** MEP · Structural · BIM

**Learning Objectives**
- Detect hard clashes between two categories of elements using bounding box intersection
- Generate a structured clash report listing conflicting element pairs
- Understand the limitations of bounding-box clash detection vs solid geometry intersection

**Key Nodes & Concepts**
`All Elements of Category` (two sets) · `Element.BoundingBox` · `BoundingBox.Intersects` · `List.AllIndicesOf` · `Data.ExportExcel` (clash report)

**Practical Example**
Retrieve all Ducts and all Structural Framing elements. Generate bounding boxes for each. Loop every duct against every beam using nested `List.Map` and `BoundingBox.Intersects` — producing a true/false matrix. Extract clashing pairs: Duct ID | Beam ID | Duct Name | Beam Name. Export to Excel. Discuss false positives from diagonal/curved geometry.

---

### Session 22 — Model QA — Finding Missing or Inconsistent Data

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Build Dynamo routines that automatically validate model data against defined rules
- Flag elements with null, blank, or out-of-range parameter values
- Produce a QA summary report and optionally mark failing elements with a flag parameter

**Key Nodes & Concepts**
`Element.GetParameterValueByName` · `== null` check / `String.Length == 0` · `FilterByBoolMask` · `Data.ExportExcel` · `Element.SetParameterByName` (QA flag Yes/No)

**Practical Example**
Define three rules for Rooms: Name not empty, Number not empty, Area > 1 m². Check each rule, combine boolean results with AND. Filter failing rooms. Export: Room ID | Name | Number | Fail Reason. Write 'Yes' to a 'QA_Fail' shared parameter so failing rooms appear red in a colour-coded Room Schedule.

---

### Session 23 — Room/Space and Equipment Data Coordination

**Disciplines:** MEP · Architecture · BIM

**Learning Objectives**
- Match MEP equipment or furniture to the room or space they physically occupy
- Use spatial containment logic to automate the room-to-element relationship
- Transfer room name and number to contained elements for accurate scheduling

**Key Nodes & Concepts**
`All Elements of Category: Rooms / Spaces` · `Element.Location` (equipment point) · `BoundingBox.Contains` · `Element.SetParameterByName` (equipment ← room data)

**Practical Example**
Retrieve all Mechanical Equipment and all Rooms. For each piece of equipment, test whether its location point falls inside a room's bounding box using `BoundingBox.Contains`. Write the matched room's 'Number' and 'Name' to the equipment's instance parameters. Verify in a Mechanical Equipment Schedule.

---

### Session 24 — Automating View Template Assignments

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Apply view templates to large sets of views in a single Dynamo run
- Filter views by type, name pattern, or other criteria before assigning templates
- Enforce visual standards firm-wide without manually opening every view

**Key Nodes & Concepts**
`All Elements of Category: Views` · `Element.Name` (filter by string) · View Template retrieval by name · `Element.SetParameterByName` (View Template parameter)

**Practical Example**
Retrieve all views, filter to Floor Plans starting with 'ARCH-'. Retrieve the 'Production – Plan' view template element and get its ElementId. Use `Element.SetParameterByName` with 'View Template' to assign it to all filtered plan views. A project with 200 views can be fully templated in under 30 seconds.

---

### Session 25 — Working with Linked Models in Dynamo

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Access and query elements from linked Revit models within a Dynamo graph
- Compare data between the host model and a linked model to detect discrepancies
- Use Excel as an intermediate bridge when direct cross-model parameter writing is not possible

**Key Nodes & Concepts**
`RevitLinkInstance` (select link) · `Document.GetElements` (from link) · `Element.GetParameterValueByName` (linked elements) · List comparison nodes · `Data.ExportExcel` (cross-model report)

**Practical Example**
In a structural model with the architectural model linked in, retrieve all Level elements from both documents. Compare level names and elevations side-by-side. Flag any level that exists in one model but not the other, or where elevations differ by more than 1 mm. Export the discrepancy report for the coordination meeting.

---

### Session 26 — Batch Placing Views on Sheets

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Automate viewport creation by placing views onto their target sheets via Dynamo
- Match views to sheets using a naming convention or an external Excel mapping
- Define consistent placement coordinates for viewports on the sheet

**Key Nodes & Concepts**
`Viewport.Create` · `All Elements of Category: Views + Sheets` · String matching (view name ↔ sheet name) · Point (placement coordinate on sheet) · `Data.ImportExcel` (optional mapping)

**Practical Example**
Retrieve all Floor Plan views named 'ARCH - Level X Plan' and all Sheets named 'Level X – Floor Plan'. Match them by extracting the level number from each name. Call `Viewport.Create` with the sheet, view, and a fixed placement point. Every plan view is now placed. Discuss sheet coordinate origin (bottom-left corner).

---

### Session 27 — Organising Graphs and Best Practices

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Organise a Dynamo graph into clearly labelled sections for team readability
- Apply colour-coded groups, canvas notes, and consistent node naming
- Optimise graph performance by disabling unnecessary previews and controlling run order

**Key Nodes & Concepts**
`Group tool` (Ctrl+G) · Canvas Notes (double-click canvas) · Node renaming (F2 on node) · Preview toggle (right-click node) · Run mode selection

**Practical Example**
Refactor the Session 13 sheet-creation graph. Create three groups: INPUT (green), PROCESS (blue), OUTPUT (orange). Add a Canvas Note at the top with purpose and run instructions. Rename the file path node and title block selector. Disable geometry preview. Switch to Manual run mode.

---

### Session 28 — Dynamo Player and Script Deployment

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Use Dynamo Player to run scripts without exposing the Dynamo graph editor to end users
- Configure Input nodes so Player presents them as a simple form interface
- Plan a deployment strategy for distributing Dynamo scripts across a project team

**Key Nodes & Concepts**
Dynamo Player (Manage tab in Revit) · Input node naming convention ('Input:' prefix group) · `Integer Slider` / `Number Slider` / `String Input` / `Bool Toggle` · File path (network drive)

**Practical Example**
Take the Session 12 view-creation graph. Add three inputs: String for 'Prefix for view names', Bool toggle for 'Also apply view template?', and String for 'View template name'. Open Dynamo Player in Revit — it shows only the input controls, no nodes or wires. A project architect fills in the fields and clicks play. Discuss deployment on shared network folders.

---

### Session 29 — Placing Elements from External Data (Coordinates)

**Disciplines:** Architecture · MEP · Structural

**Learning Objectives**
- Drive the placement of Revit family instances using XYZ coordinate data from Excel
- Handle coordinate system considerations (project coordinates vs survey coordinates)
- Verify placed elements against source data for accuracy

**Key Nodes & Concepts**
`Data.ImportExcel` (X, Y, Level columns) · `FamilyInstance.ByPoint` · `FamilyInstance.ByCoordinates` (with Level) · Family Type selection · `Point.ByCoordinates`

**Practical Example**
Prepare an Excel file with columns: X (mm), Y (mm), Level Name, Fixture Type. Import, convert to Dynamo units, build placement points with `Point.ByCoordinates`. Select the target FamilyType (e.g. 'Downlight – Recessed 100mm'). Call `FamilyInstance.ByPoint` to place all 80 fixtures in one run. Verify by comparing Watch output count to Excel row count.

---

### Session 30 — Final Project — Integrated Workflow Capstone

**Disciplines:** Architecture · MEP · Structural · BIM

**Learning Objectives**
- Combine techniques from across the course into one coherent end-to-end workflow
- Plan a multi-step automation sequence and execute it methodically
- Reflect on the value delivered and identify which techniques apply to your own projects

**Key Nodes & Concepts**
All prior session techniques · Excel I/O · Selection + filtering + parameter set · View + sheet creation + viewport placement · QA export

**Practical Example**
**New Project Setup and QA Pipeline:**
1. Read an Excel project setup file with level names, sheet index, and room programme
2. Create Floor Plan views per level and apply view templates (Sessions 12 + 24)
3. Create all drawing sheets from the sheet index (Session 13)
4. Place plan views onto sheets at a defined position (Session 26)
5. Write room programme data to Room parameters (Session 10)
6. Run a QA check for empty room parameters and export warnings to Excel (Session 22)

The full pipeline — from blank project to documented, checked, sheet-ready model — runs in under 3 minutes.

---

## Course Summary

| Phase | Sessions | Duration | Core Focus |
|---|---|---|---|
| Beginner | 01–08 | 160 min | Interface, data types, selection, filtering, parameter read/write, list management, code blocks |
| Intermediate | 09–20 | 240 min | Excel I/O, calculations, view/sheet creation, naming, renumbering, tagging, QA/QC, geometry |
| Advanced | 21–30 | 200 min | Clash detection, data validation, room coordination, view templates, linked models, deployment |
| **Total** | **30** | **600 min (10 hrs)** | |
