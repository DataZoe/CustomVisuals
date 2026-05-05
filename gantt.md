# Gantt Chart Visual for Power BI

A powerful, feature-rich Gantt chart custom visual for Microsoft Power BI that helps you visualize project timelines, track task dependencies, and identify critical paths.

![Gantt Chart Visual](icon.png)

## Live Demo

[![View Live Demo](https://img.shields.io/badge/View%20Live%20Demo-Power%20BI-F2C811?style=for-the-badge&logo=powerbi)](https://app.powerbi.com/view?r=eyJrIjoiYmFhYTMyOTItOTJkYS00MTA2LWE4YzItMWI3ZGJmOGI2OWU2IiwidCI6IjkyOWVlMzI0LTk3YzQtNDk1YS04MjM5LTZhZDg3NDk0MGVlYyIsImMiOjN9)

👉 **[Click here to explore the interactive Gantt chart demo](https://app.powerbi.com/view?r=eyJrIjoiYmFhYTMyOTItOTJkYS00MTA2LWE4YzItMWI3ZGJmOGI2OWU2IiwidCI6IjkyOWVlMzI0LTk3YzQtNDk1YS04MjM5LTZhZDg3NDk0MGVlYyIsImMiOjN9)**

## What is a Gantt Chart?

A Gantt chart is a horizontal bar chart used in project management to visualize a project schedule. Each task is represented as a horizontal bar, with the bar's position and length indicating the task's start date, end date, and duration. Gantt charts make it easy to see:

- **What** tasks need to be completed
- **When** each task starts and ends
- **How long** each task takes
- **Which tasks** depend on others
- **Where** tasks overlap
- **The critical path** through your project

## Key Benefits

### 📊 Visual Project Timeline

See your entire project at a glance with tasks displayed on a timeline. Quickly identify scheduling conflicts, gaps, and resource allocation issues.

### 🔗 Dependency Tracking

Define task dependencies to visualize which tasks must complete before others can begin. Dependency arrows show the flow of work through your project.

### 🚨 Critical Path Analysis

Automatically identifies and highlights the critical path—the longest sequence of dependent tasks that determines the minimum project duration. Any delay on critical path tasks delays the entire project.

### ⚠️ Slipped Task Detection

Tasks that have been pushed past their original dates due to dependencies are automatically highlighted, making it easy to identify schedule impacts.

### 🎯 Milestone Support

Tasks without an end date (or with the same start and end date) are displayed as diamond-shaped milestones, perfect for marking key project deliverables.

### 📈 Progress Tracking

Add a Progress % field to show task completion as an overlay bar on each task. The progress bar fills from left to right based on the percentage (0-100).

### 📍 Custom Marker Lines

Add one or more date measures to display vertical marker lines on the chart. Perfect for deadlines, milestones, phase gates, or any significant dates. Each marker shows the measure name as a label.

### 📁 Category Grouping

Organize tasks into collapsible categories for better organization of large projects. Summary bars show the span of each category.

### 👥 Resource Tracking & Conflict Detection

Assign a resource to each task and the visual will:

- Display resources in a dedicated column
- Detect **resource conflicts** — when the same resource is assigned to overlapping tasks, both cells get a colored pill and a tooltip listing the conflicting tasks
- Let you **click a resource** to focus on its rows; everything else dims, making it easy to scan one person/team's workload

### ⏱️ Relative-Units Mode

Use a numeric Start/End instead of dates to chart schedules in hours, minutes, days, weeks, months, or years. Perfect for event run-of-show, manufacturing cycles, or any process where calendar dates aren't meaningful.

### 📅 Flexible Time Scale

Control how the date axis displays with the **Auto time scale** toggle. When on (default), the visual selects day, week, month, quarter, or year intervals based on your date range. Turn it off to manually choose a primary unit and optionally add a secondary tier for hierarchical grouping (e.g., weeks under months, months under years).

### 🔍 Context Column Filtering

Add additional columns (like Status, Owner, Priority) to display alongside tasks. Click column headers to open a multi-select filter popup with checkboxes. Filter by multiple values, including blank entries. Filters apply instantly and show active filter status in the header.
*Note: The filter popup is constrained within the visual container (a limitation of Power BI custom visuals). Ensure your visual has sufficient size for the popup to display properly.*
### ♿ Accessibility Features

- Full keyboard navigation support
- High-contrast mode compatibility
- Screen reader friendly with ARIA attributes
- Multi-language localization (English, Spanish, French, German, Portuguese)

### 🎨 Extensive Customization

- Theme color palette integration
- Customizable bar colors, borders, and opacity
- Adjustable fonts, sizes, and spacing
- Grid lines and date header formatting
- Critical path styling options

## Data Fields

| Field | Required | Description |
|-------|----------|-------------|
| **Task** | ✅ Yes | Task name or description displayed on the chart |
| **Start Date** | Optional | When the task begins. Accepts a date OR a numeric value (relative-units mode). If missing, visual uses a default 30-day timeline |
| **End Date** | Optional | When the task ends. If empty, task appears as a milestone. Must match the type of Start Date (date OR numeric) |
| **Category** | Optional | Groups tasks into collapsible sections |
| **Task ID** | Optional | Unique identifier for dependency linking |
| **Dependencies** | Optional | Comma-separated Task IDs that must complete first |
| **Progress %** | Optional | Task completion percentage (0-100). Displays as progress bar overlay |
| **Resource** | Optional | Person/team assigned to the task. Shown in a dedicated column. Click a resource to focus its rows; conflicts (same resource, overlapping dates) get a colored pill in the cell |
| **Marker Dates** | Optional | Custom dates for vertical marker lines. Add multiple measures |
| **Context Columns** | Optional | Additional columns displayed alongside tasks. Click headers to filter with multi-select checkboxes |
| **Tooltips** | Optional | Additional data fields to show in tooltips |

## How to Use

### Step 1: Add the Visual to Your Report

1. In Power BI Desktop, go to the **Visualizations** pane
2. Click the **...** (more options) button
3. Select **Import a visual from a file**
4. Browse to the `.pbiviz` file and click **Open**
5. The Gantt chart icon will appear in your visualizations pane

### Step 2: Prepare Your Data

Your data should be in a table format with at minimum:

- A column for task names

Optionally include:

- Start dates (if missing, a default 30-day timeline is used)

- End dates
- Task IDs (for dependencies)
- Dependencies (referencing Task IDs)
- Categories

### Step 3: Add Data to the Visual

1. Click the Gantt chart visual to select it
2. Drag your fields to the appropriate data wells:
   - **Task**: Your task name column
   - **Start Date**: Your start date column
   - **End Date**: Your end date column (optional)
   - **Task ID**: Your unique identifier column (optional)
   - **Dependencies**: Your dependencies column (optional)
   - **Category**: Your category/phase column (optional)
   - **Progress %**: Your completion measure (optional)
   - **Resource**: Your assigned person/team column (optional)

### Step 4: Customize Appearance

1. With the visual selected, click the **Format** pane (paint roller icon)
2. Expand the formatting cards to customize:
   - **Style presets**: Quick layout/spacing presets
   - **Layout**: Axis & column positions, zoom controls visibility
   - **Axis**: Auto/manual time scale, relative units, axis title, grid lines, divider, row & day shading
   - **Columns**: Task / Context / Resource column fonts, colors, widths
   - **Bars**: Colors, borders, opacity, height, duration label, progress overlay
   - **Milestones**: Shape, color, size
   - **Top level timeline / Category timeline**: Summary roll-up rows above the chart and per-category
   - **Markers**: Today line and any custom Marker Date measures
   - **Analytics**: Dependencies, Critical path, Slippage, Resource conflicts

### Step 5: Interact with the Chart

- **Click** a task to select it and cross-filter other visuals
- **Ctrl+Click** to select multiple tasks
- **Click** category headers to expand/collapse groups
- **Click** a context column header (with the ▾ caret) to open a multi-select filter
- **Click** a resource cell to focus that resource (other rows dim); click empty space to clear
- **Use the Critical Path / Slippage / Resource conflicts toggles** at the bottom of the chart
- **Right-click** for context menu options
- **Use Tab/Arrow keys** for keyboard navigation

## Example: Software Development Project

### Sample Data

Copy this data into Excel or create it in Power BI:

| TaskID | Category | Task | StartDate | EndDate | Dependencies | Progress |
|--------|----------|------|-----------|---------|--------------|----------|
| 1 | Planning | Project Kickoff | 2025-01-06 | 2025-01-06 | | 100 |
| 2 | Planning | Requirements Gathering | 2025-01-07 | 2025-01-17 | 1 | 100 |
| 3 | Planning | Technical Specification | 2025-01-13 | 2025-01-24 | 2 | 75 |
| 4 | Planning | Architecture Review | 2025-01-27 | 2025-01-27 | 3 | 0 |
| 5 | Development | Database Design | 2025-01-28 | 2025-02-07 | 4 | 50 |
| 6 | Development | API Development | 2025-02-03 | 2025-02-21 | 5 | 25 |
| 7 | Development | Frontend Development | 2025-02-10 | 2025-02-28 | 5 | 10 |
| 8 | Development | Integration | 2025-02-24 | 2025-03-07 | 6, 7 | 0 |
| 9 | Testing | Unit Testing | 2025-02-17 | 2025-03-07 | 6 | 0 |
| 10 | Testing | Integration Testing | 2025-03-10 | 2025-03-21 | 8, 9 | 0 |
| 11 | Testing | User Acceptance Testing | 2025-03-24 | 2025-04-04 | 10 | 0 |
| 12 | Deployment | Production Deployment | 2025-04-07 | 2025-04-11 | 11 | 0 |
| 13 | Deployment | Go Live | 2025-04-14 | 2025-04-14 | 12 | 0 |

### Marker Date Measures

Create these DAX measures to add milestone markers:

```dax
Project Start = DATE(2025, 1, 6)
Phase 2 Start = DATE(2025, 1, 28)
Go Live Target = DATE(2025, 4, 14)
```

### Step-by-Step Instructions

1. **Create a new Power BI report** and import the sample data above

2. **Add the Gantt visual** to your report canvas

3. **Configure the data fields:**
   - Drag `Task` to the **Task** field
   - Drag `StartDate` to the **Start Date** field
   - Drag `EndDate` to the **End Date** field
   - Drag `TaskID` to the **Task ID** field
   - Drag `Dependencies` to the **Dependencies** field
   - Drag `Category` to the **Category** field
   - Drag `Progress` to the **Progress %** field

4. **Add marker date measures:**
   - Create the DAX measures shown above
   - Drag `Project Start`, `Phase 2 Start`, and `Go Live Target` to the **Marker Dates** field
   - Each marker appears as a vertical line with its measure name as a label

5. **Observe the results:**
   - Tasks are grouped by category (Planning, Development, Testing, Deployment)
   - Milestones (Project Kickoff, Architecture Review, Go Live) appear as diamonds
   - Progress bars show completion status on each task
   - Marker lines highlight key project dates
   - Dependency arrows connect related tasks
   - The critical path is highlighted

6. **Toggle the Critical Path:**
   - Click the "Critical Path" toggle button in the chart header
   - Tasks on the critical path are highlighted with a colored border
   - The summary shows total critical path duration

7. **Explore the categories:**
   - Click the ▼ arrow next to "Development" to collapse that section
   - Click again to expand
   - Notice the summary bar showing the category's time span

### DAX Calculated Table

Alternatively, create the sample data directly in Power BI using a DAX calculated table:

```dax
SoftwareProject = 
VAR TaskTable = 
    {
        ( 1, "Project Kickoff", "Planning", DATE(2025,1,6), DATE(2025,1,6), 100, "" ),
        ( 2, "Requirements Gathering", "Planning", DATE(2025,1,7), DATE(2025,1,17), 100, "1" ),
        ( 3, "Technical Specification", "Planning", DATE(2025,1,13), DATE(2025,1,24), 75, "2" ),
        ( 4, "Architecture Review", "Planning", DATE(2025,1,27), DATE(2025,1,27), 0, "3" ),
        ( 5, "Database Design", "Development", DATE(2025,1,28), DATE(2025,2,7), 50, "4" ),
        ( 6, "API Development", "Development", DATE(2025,2,3), DATE(2025,2,21), 25, "5" ),
        ( 7, "Frontend Development", "Development", DATE(2025,2,10), DATE(2025,2,28), 10, "5" ),
        ( 8, "Integration", "Development", DATE(2025,2,24), DATE(2025,3,7), 0, "6,7" ),
        ( 9, "Unit Testing", "Testing", DATE(2025,2,17), DATE(2025,3,7), 0, "6" ),
        ( 10, "Integration Testing", "Testing", DATE(2025,3,10), DATE(2025,3,21), 0, "8,9" ),
        ( 11, "User Acceptance Testing", "Testing", DATE(2025,3,24), DATE(2025,4,4), 0, "10" ),
        ( 12, "Production Deployment", "Deployment", DATE(2025,4,7), DATE(2025,4,11), 0, "11" ),
        ( 13, "Go Live", "Deployment", DATE(2025,4,14), DATE(2025,4,14), 0, "12" )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6],
        "Dependencies", [Value7]
    )
```

## Example: Marketing Campaign

### Sample Data

| TaskID | Category | Task | StartDate | EndDate | Dependencies | Progress |
|--------|----------|------|-----------|---------|--------------|----------|
| M1 | Strategy | Campaign Brief | 2025-02-03 | 2025-02-07 | | 100 |
| M2 | Strategy | Target Audience Research | 2025-02-10 | 2025-02-14 | M1 | 100 |
| M3 | Strategy | Budget Approval | 2025-02-17 | 2025-02-17 | M2 | 100 |
| M4 | Creative | Concept Development | 2025-02-18 | 2025-02-28 | M3 | 80 |
| M5 | Creative | Copywriting | 2025-02-24 | 2025-03-07 | M4 | 60 |
| M6 | Creative | Design Assets | 2025-02-24 | 2025-03-14 | M4 | 45 |
| M7 | Creative | Video Production | 2025-03-03 | 2025-03-21 | M4 | 30 |
| M8 | Digital | Landing Page | 2025-03-10 | 2025-03-21 | M5, M6 | 15 |
| M9 | Digital | Email Templates | 2025-03-10 | 2025-03-17 | M5 | 20 |
| M10 | Digital | Social Media Setup | 2025-03-17 | 2025-03-21 | M6 | 0 |
| M11 | Launch | Soft Launch | 2025-03-24 | 2025-03-28 | M8, M9, M10, M7 | 0 |
| M12 | Launch | Full Campaign Launch | 2025-03-31 | 2025-03-31 | M11 | 0 |
| M13 | Launch | Performance Review | 2025-04-14 | 2025-04-18 | M12 | 0 |

### Key Observations

- **M3 (Budget Approval)** and **M12 (Full Campaign Launch)** are milestones
- **Creative** tasks can run in parallel after Concept Development
- The critical path likely runs through the longest creative task (Video Production)
- **Soft Launch** depends on multiple tasks completing

### DAX Calculated Table

```dax
MarketingCampaign = 
VAR TaskTable = 
    {
        ( "M1", "Campaign Brief", "Strategy", DATE(2025,2,3), DATE(2025,2,7), 100, "" ),
        ( "M2", "Target Audience Research", "Strategy", DATE(2025,2,10), DATE(2025,2,14), 100, "M1" ),
        ( "M3", "Budget Approval", "Strategy", DATE(2025,2,17), DATE(2025,2,17), 100, "M2" ),
        ( "M4", "Concept Development", "Creative", DATE(2025,2,18), DATE(2025,2,28), 80, "M3" ),
        ( "M5", "Copywriting", "Creative", DATE(2025,2,24), DATE(2025,3,7), 60, "M4" ),
        ( "M6", "Design Assets", "Creative", DATE(2025,2,24), DATE(2025,3,14), 45, "M4" ),
        ( "M7", "Video Production", "Creative", DATE(2025,3,3), DATE(2025,3,21), 30, "M4" ),
        ( "M8", "Landing Page", "Digital", DATE(2025,3,10), DATE(2025,3,21), 15, "M5,M6" ),
        ( "M9", "Email Templates", "Digital", DATE(2025,3,10), DATE(2025,3,17), 20, "M5" ),
        ( "M10", "Social Media Setup", "Digital", DATE(2025,3,17), DATE(2025,3,21), 0, "M6" ),
        ( "M11", "Soft Launch", "Launch", DATE(2025,3,24), DATE(2025,3,28), 0, "M8,M9,M10,M7" ),
        ( "M12", "Full Campaign Launch", "Launch", DATE(2025,3,31), DATE(2025,3,31), 0, "M11" ),
        ( "M13", "Performance Review", "Launch", DATE(2025,4,14), DATE(2025,4,18), 0, "M12" )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6],
        "Dependencies", [Value7]
    )
```

## Example: Construction Project

### Sample Data

| TaskID | Category | Task | StartDate | EndDate | Dependencies | Progress |
|--------|----------|------|-----------|---------|--------------|----------|
| C1 | Permits | Site Survey | 2025-03-03 | 2025-03-14 | | 100 |
| C2 | Permits | Permit Application | 2025-03-17 | 2025-03-28 | C1 | 100 |
| C3 | Permits | Permit Approved | 2025-04-14 | 2025-04-14 | C2 | 100 |
| C4 | Foundation | Excavation | 2025-04-15 | 2025-04-25 | C3 | 100 |
| C5 | Foundation | Foundation Pour | 2025-04-28 | 2025-05-02 | C4 | 100 |
| C6 | Foundation | Curing Period | 2025-05-05 | 2025-05-16 | C5 | 75 |
| C7 | Structure | Framing | 2025-05-19 | 2025-06-13 | C6 | 50 |
| C8 | Structure | Roofing | 2025-06-16 | 2025-06-27 | C7 | 20 |
| C9 | Structure | Windows & Doors | 2025-06-23 | 2025-07-03 | C7 | 10 |
| C10 | Systems | Electrical Rough-in | 2025-06-30 | 2025-07-18 | C8 | 0 |
| C11 | Systems | Plumbing Rough-in | 2025-06-30 | 2025-07-18 | C8 | 0 |
| C12 | Systems | HVAC Installation | 2025-07-07 | 2025-07-25 | C8 | 0 |
| C13 | Interior | Insulation | 2025-07-21 | 2025-07-30 | C10, C11 | 0 |
| C14 | Interior | Drywall | 2025-08-01 | 2025-08-15 | C13 | 0 |
| C15 | Interior | Painting | 2025-08-18 | 2025-08-29 | C14 | 0 |
| C16 | Interior | Flooring | 2025-09-01 | 2025-09-12 | C15 | 0 |
| C17 | Finishing | Fixtures & Appliances | 2025-09-15 | 2025-09-26 | C16, C12 | 0 |
| C18 | Finishing | Final Inspection | 2025-09-29 | 2025-09-29 | C17 | 0 |
| C19 | Finishing | Certificate of Occupancy | 2025-10-06 | 2025-10-06 | C18 | 0 |

### Key Features Demonstrated

- **Long dependency chains** show the sequential nature of construction
- **Parallel work** in the Systems phase (Electrical, Plumbing, HVAC)
- **Milestone dates** for permit approval, inspection, and certificate
- **Critical path** identifies which delays would impact completion

### DAX Calculated Table

```dax
ConstructionProject = 
VAR TaskTable = 
    {
        ( "C1", "Site Survey", "Permits", DATE(2025,3,3), DATE(2025,3,14), 100, "" ),
        ( "C2", "Permit Application", "Permits", DATE(2025,3,17), DATE(2025,3,28), 100, "C1" ),
        ( "C3", "Permit Approved", "Permits", DATE(2025,4,14), DATE(2025,4,14), 100, "C2" ),
        ( "C4", "Excavation", "Foundation", DATE(2025,4,15), DATE(2025,4,25), 100, "C3" ),
        ( "C5", "Foundation Pour", "Foundation", DATE(2025,4,28), DATE(2025,5,2), 100, "C4" ),
        ( "C6", "Curing Period", "Foundation", DATE(2025,5,5), DATE(2025,5,16), 75, "C5" ),
        ( "C7", "Framing", "Structure", DATE(2025,5,19), DATE(2025,6,13), 50, "C6" ),
        ( "C8", "Roofing", "Structure", DATE(2025,6,16), DATE(2025,6,27), 20, "C7" ),
        ( "C9", "Windows & Doors", "Structure", DATE(2025,6,23), DATE(2025,7,3), 10, "C7" ),
        ( "C10", "Electrical Rough-in", "Systems", DATE(2025,6,30), DATE(2025,7,18), 0, "C8" ),
        ( "C11", "Plumbing Rough-in", "Systems", DATE(2025,6,30), DATE(2025,7,18), 0, "C8" ),
        ( "C12", "HVAC Installation", "Systems", DATE(2025,7,7), DATE(2025,7,25), 0, "C8" ),
        ( "C13", "Insulation", "Interior", DATE(2025,7,21), DATE(2025,7,30), 0, "C10,C11" ),
        ( "C14", "Drywall", "Interior", DATE(2025,8,1), DATE(2025,8,15), 0, "C13" ),
        ( "C15", "Painting", "Interior", DATE(2025,8,18), DATE(2025,8,29), 0, "C14" ),
        ( "C16", "Flooring", "Interior", DATE(2025,9,1), DATE(2025,9,12), 0, "C15" ),
        ( "C17", "Fixtures & Appliances", "Finishing", DATE(2025,9,15), DATE(2025,9,26), 0, "C16,C12" ),
        ( "C18", "Final Inspection", "Finishing", DATE(2025,9,29), DATE(2025,9,29), 0, "C17" ),
        ( "C19", "Certificate of Occupancy", "Finishing", DATE(2025,10,6), DATE(2025,10,6), 0, "C18" )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6],
        "Dependencies", [Value7]
    )
```

## DAX Table Constructor Reference

Each example above includes a DAX calculated table version. Here's how to use them:

### How to Create a DAX Table

1. In Power BI Desktop, go to **Modeling** → **New table**
2. Paste any of the DAX formulas from the examples above
3. Add the Gantt visual and drag the columns to the appropriate fields:
   - **Task** → Task
   - **Start** → Start Date
   - **End** → End Date
   - **Task ID** → Task ID
   - **Dependencies** → Dependencies
   - **Category** → Category
   - **Progress** → Progress %

### Why Table Constructors?

This approach uses table constructors `{ ( ... ), ( ... ) }` instead of `DATATABLE()` because `DATATABLE` doesn't support expressions like `DATE()`. Table constructors allow you to use any DAX expression for values, making them ideal for sample data with calculated dates.

### Quick Start Example

```dax
GanttData = 
VAR TaskTable = 
    {
        ( 1, "Project Kickoff", "Planning", DATE(2026,1,6), DATE(2026,1,6), 100, "" ),
        ( 2, "Requirements Gathering", "Planning", DATE(2026,1,7), DATE(2026,1,14), 100, "1" ),
        ( 3, "Requirements Sign-off", "Planning", DATE(2026,1,15), DATE(2026,1,15), 100, "2" ),
        ( 4, "Design Phase", "Design", DATE(2026,1,16), DATE(2026,1,28), 75, "3" ),
        ( 5, "UI Mockups", "Design", DATE(2026,1,20), DATE(2026,1,31), 60, "3" ),
        ( 6, "Database Design", "Design", DATE(2026,1,22), DATE(2026,2,5), 40, "4" ),
        ( 7, "Design Review", "Design", DATE(2026,2,6), DATE(2026,2,6), 0, "5,6" ),
        ( 8, "Backend Development", "Development", DATE(2026,2,9), DATE(2026,2,28), 25, "7" ),
        ( 9, "Frontend Development", "Development", DATE(2026,2,10), DATE(2026,3,10), 10, "7" ),
        ( 10, "API Integration", "Development", DATE(2026,2,15), DATE(2026,3,5), 0, "8" ),
        ( 11, "Code Complete", "Development", DATE(2026,3,11), DATE(2026,3,11), 0, "9,10" ),
        ( 12, "Testing", "QA", DATE(2026,3,12), DATE(2026,3,20), 0, "11" ),
        ( 13, "Bug Fixes", "QA", DATE(2026,3,21), DATE(2026,3,27), 0, "12" ),
        ( 14, "Documentation", "Deployment", DATE(2026,3,12), DATE(2026,3,28), 0, "11" ),
        ( 15, "Go Live", "Deployment", DATE(2026,3,30), DATE(2026,3,30), 0, "13,14" )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6],
        "Dependencies", [Value7]
    )
```

### Handling Missing Dates

When tasks have missing or invalid start dates, the visual gracefully handles these scenarios:

- **Tasks without dates**: Tasks with missing start dates are still displayed. The visual uses a default 30-day date range (starting from today) when no valid dates exist in the dataset.
- **Partial data**: Even if some tasks have dates and others don't, all tasks are shown. Tasks without dates appear at a default position.

This is useful when you have a task list that's still being planned and doesn't have dates assigned yet.

#### Sample Data with Missing Dates

| TaskID | Category | Task | StartDate | EndDate | Progress |
|--------|----------|------|-----------|---------|----------|
| 1 | Backlog | Review requirements | | | 0 |
| 2 | Backlog | Define acceptance criteria | | | 0 |
| 3 | Backlog | Estimate effort | | | 0 |
| 4 | In Progress | Build login page | 2025-03-03 | 2025-03-07 | 50 |
| 5 | In Progress | Create API endpoints | 2025-03-05 | 2025-03-12 | 25 |
| 6 | Done | Setup project | 2025-02-24 | 2025-02-28 | 100 |

#### DAX Table with Missing Dates

```dax
TasksWithMissingDates = 
VAR TaskTable = 
    {
        ( 1, "Review requirements", "Backlog", BLANK(), BLANK(), 0 ),
        ( 2, "Define acceptance criteria", "Backlog", BLANK(), BLANK(), 0 ),
        ( 3, "Estimate effort", "Backlog", BLANK(), BLANK(), 0 ),
        ( 4, "Build login page", "In Progress", DATE(2025,3,3), DATE(2025,3,7), 50 ),
        ( 5, "Create API endpoints", "In Progress", DATE(2025,3,5), DATE(2025,3,12), 25 ),
        ( 6, "Setup project", "Done", DATE(2025,2,24), DATE(2025,2,28), 100 )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6]
    )
```

#### All Tasks Without Dates

If your entire dataset has no dates (e.g., a backlog of unscheduled work), the visual still renders with a default 30-day timeline:

```dax
UnscheduledBacklog = 
VAR TaskTable = 
    {
        ( 1, "User authentication", "Security", BLANK(), BLANK(), 0 ),
        ( 2, "Password reset flow", "Security", BLANK(), BLANK(), 0 ),
        ( 3, "Dashboard widgets", "UI", BLANK(), BLANK(), 0 ),
        ( 4, "Export to PDF", "Features", BLANK(), BLANK(), 0 ),
        ( 5, "Email notifications", "Features", BLANK(), BLANK(), 0 )
    }
RETURN
    SELECTCOLUMNS(
        TaskTable,
        "Task ID", [Value1],
        "Task", [Value2],
        "Category", [Value3],
        "Start", [Value4],
        "End", [Value5],
        "Progress", [Value6]
    )
```

## Sample Datasets (TMDL)

The repo ships two ready-to-use TMDL scripts under `assets/sample-data/`. In Power BI Desktop with TMDL view enabled, paste either script as a new table to instantly demo every analytics feature.

### Calendar_ProductLaunch.tmdl

A 12-task product launch on real calendar dates (April–June 2026). Demonstrates:

- **Critical path**: 1 → 2 → 4 → 6 → 8 → 10 → 11
- **Slippage**: tasks 4, 6, and 8 have `EndDate > PlannedEnd`
- **Resource conflicts** (intentional):
  - Resource A double-booked May 11–22 (tasks 4 and 5)
  - Resource D double-booked May 22–28 (tasks 8 and 9)
- **Milestones**: task 0 (Kickoff) and task 11 (GA release)
- **Categories**: Discovery / Build / Launch
- **Marker measures**: Kickoff, Code freeze, GA target, Latest planned end, Latest actual end

Bind the columns: `Task` → Task, `StartDate` → Start, `EndDate` → End, `TaskId` → Task ID, `Dependencies` → Dependencies, `Category` → Category, `Resource` → Resource, `Progress` → Progress %, `Tooltip_Notes` → Tooltips.

### RelativeUnits_LaunchDay.tmdl

A single-day event run-of-show with numeric (hour-offset) Start/End values. Demonstrates:

- **Relative-units mode** rendering with hour suffixes
- **Resource conflict** (Resource A on Keynote vs Press Q&A)
- Sub-task IDs and dependencies

In the visual's settings, set Start/End units to **Hour** and pick the appropriate origin.



### Data Preparation

- Use consistent date formats
- Keep Task IDs unique and simple (numbers or short codes)
- Use comma-separated values for multiple dependencies
- Leave End Date empty for milestones
- Tasks with missing start dates will still appear (using a default timeline)

### Visual Design

- Use categories to organize large projects
- Enable the color palette for automatic task coloring by category
- Adjust bar height and row spacing for readability
- Use high-contrast colors for critical path highlighting

### Interactivity

- Combine with slicers to filter by date range or category
- Use cross-filtering with other visuals for project dashboards
- Export to PDF/PowerPoint for stakeholder presentations

## Formatting Options Reference

The format pane is organized into ten cards (in display order: **Style presets, Layout, Axis, Columns, Bars, Milestones, Top level timeline, Category timeline, Markers, Analytics**).

---

### 1. Style presets

Quick layout adjustments using presets.

| Setting | Description | Default |
|---------|-------------|---------|
| Preset | Quick style presets for bar height, spacing, and corner radius | Default |

**Available presets:**

| Preset | Bar Height | Row Spacing | Corner Radius |
|--------|------------|-------------|---------------|
| Default | 14px | 2px | 4px |
| Comfortable | 18px | 4px | 6px |
| Relaxed | 24px | 8px | 8px |
| Spacious | 32px | 12px | 10px |

*Note: After selecting a preset, you can manually adjust individual settings in the Bars card. The preset only applies values when you change it.*

---

### 2. Layout

Controls where the date axis and the various label columns are placed around the chart, plus on-canvas chrome (zoom controls).

#### Position Group

| Setting | Description | Default |
|---------|-------------|---------|
| Axis position | Show the date axis at the top, bottom, or both | Bottom |
| Task column | Place the Task column on the left or right of the chart | Left |
| Context columns | Place context columns on the left or right of the chart | Left |
| Resource column | Place the Resource column on the left or right of the chart | Left |

#### Zoom controls Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show | Show the zoom +/− buttons on the chart | On |

---

### 3. Axis

Date axis units (calendar or relative), axis title, grid lines, divider, row banding and day shading — all in one composite card.

#### Units Group

*Disabled when Start/End columns are numeric (relative-units mode).*

| Setting | Description | Default |
|---------|-------------|---------|
| Auto time scale | When On, the visual picks the best fit automatically. Turn Off to choose units manually. | On |
| Primary unit | Main time unit for labels and grid lines (Day / Week / Month / Quarter / Year). Hidden when Auto is On. | Week |
| Secondary unit | Optional grouping tier above primary labels (None / Week / Month / Quarter / Year). Hidden when Auto is On. | None |
| Week starts on | First day of the week for week-unit calculations. Hidden when Auto is On. | Monday |
| Day unit min width | Minimum width per day in pixels (1–100). Hidden when Auto is On. | 10 |

**Auto mode behavior:**

| Date Range | Primary Unit | Secondary Unit |
|------------|--------------|----------------|
| ≤14 days | Day | – |
| ≤60 days | Week | Month (if >2 weeks) |
| ≤180 days | Week or Month | – |
| ≤365 days | Month | Year |
| >365 days | Month or Quarter | Year |

#### Relative Units Group

*Disabled when Start/End columns are dates. Active only when Start is numeric (relative-units mode).*

| Setting | Description | Default |
|---------|-------------|---------|
| Unit | Unit label used for relative axis ticks (Year, Month, Week, Day, Hour, Minute, Second, Step) | Day |
| Start at | Whether the first unit is labeled 0 or 1 | 1 |
| Label prefix | Text shown before each tick value (e.g. "Day ") | (empty) |
| Label suffix | Text shown after each tick value | (empty) |
| Tick interval | Spacing between major axis ticks, in units (1–1000) | 1 |

#### Axis Title Group

| Setting | Description | Default |
|---------|-------------|---------|
| Title | Show the date axis title (timeline header) | On |
| Title font | Font family, size (10–24), bold, italic, underline | Segoe UI, 14pt |
| Title color | Header text color | #242424 |

#### Primary Lines Group

| Setting | Description | Default |
|---------|-------------|---------|
| Primary lines | Show vertical lines at primary unit intervals | On |
| Color | Line color | #e0e0e0 |
| Style | Solid / Dashed / Dotted | Dashed |

#### Secondary Lines Group

| Setting | Description | Default |
|---------|-------------|---------|
| Secondary lines | Show vertical lines at secondary unit boundaries | On |
| Color | Line color | #c0c0c0 |
| Style | Solid / Dashed / Dotted | Solid |

*Secondary lines only appear when a secondary unit is configured.*

#### Divider Group

| Setting | Description | Default |
|---------|-------------|---------|
| Label divider | Vertical line separating labels from chart | On |
| Color | Divider line color | #e0e0e0 |
| Width | Divider thickness (1–5 px) | 1 |
| Style | Solid / Dashed / Dotted | Solid |

#### Row Shading Group

| Setting | Description | Default |
|---------|-------------|---------|
| Alternating rows | Display alternating row background colors | On |
| Even rows | Background color for even rows | #ffffff |
| Odd rows | Background color for odd rows | #f9f9f9 |

#### Day Shading Group

| Setting | Description | Default |
|---------|-------------|---------|
| Shade weekends | Highlight Saturday and Sunday columns | Off |
| Custom days | Comma-separated day names to shade (e.g., "Monday, Friday") | (empty) |
| Shade color | Background color for shaded day columns | #f0f0f0 |
| Shade opacity | Transparency (10–100%) | 30% |

---

### 4. Columns

The text columns that sit alongside the chart: the task name column, optional context columns, and the resource column.

#### Task column Group

| Setting | Description | Default |
|---------|-------------|---------|
| Task labels | Display task names | On |
| Font | Font family, size (8–24), bold, italic, underline | Segoe UI, 10pt |
| Color | Text color | #242424 |
| Max width | Maximum width before truncation (50–500 px) | 140 |
| Word wrap | Wrap long names to multiple lines | Off |
| Selection color | Background color when task is selected | #ebf3fc |

#### Context columns Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show | Display context columns | On |
| Font | Font family, size (6–24), bold, italic, underline | Segoe UI, 10pt |
| Color | Text color | #616161 |
| Column width | Width for each context column (50–200 px) | 80 |
| Column spacing | Spacing between columns (0–20 px) | 8 |

#### Resource column Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show | Display the resource column | On |
| Font | Font family, size (6–24), bold, italic, underline | Segoe UI, 10pt |
| Color | Text color | #424242 |
| Column width | Width of the resource column (50–300 px) | 100 |

---

### 5. Bars

Configure task bar appearance, duration labels, and progress overlays. (Milestones are now their own top-level card — see below.)

#### Appearance Group

| Setting | Description | Default |
|---------|-------------|---------|
| Theme colors | Auto-assign colors from Power BI theme based on category | Off |
| Color | Bar fill color | #0f6cbd |
| Opacity | Bar transparency (0–100%) | 100% |
| Border | Display bar border | Off |
| Border color | Border color when enabled | #0e4775 |
| Border width | Border thickness (0–5 px) | 1 |
| Height | Height of bars (10–50 px) | 14 |
| Corner radius | Rounded corners (0–20 px) | 4 |
| Row spacing | Space between rows (0–20 px) | 2 |

#### Duration label Group

| Setting | Description | Default |
|---------|-------------|---------|
| Duration label | Display duration text on bars | On |
| Font | Font family, size (6–24), bold, italic, underline | Segoe UI, 11pt, Bold |
| Color | Duration text color | #ffffff |
| Auto-contrast | Automatically adjust text color for readability against bar color | On |

#### Progress Group

| Setting | Description | Default |
|---------|-------------|---------|
| Progress overlay | Display progress bar overlay on tasks | On |
| Data format | How progress values are provided (Whole number 0-100 or Percentage 0%-100%) | Whole number (0-100) |
| Color | Progress bar color | #ffffff |
| Opacity | Progress bar transparency (10–100%) | 40% |
| Height | Height as percentage of task bar (20–100%) | 100% |
| Pattern | Fill pattern style (Solid / Diagonal stripes / Dots / Crosshatch / Horizontal lines) | Solid |

---

### 6. Milestones

Top-level card controlling how milestone (zero-duration) tasks render.

| Setting | Description | Default |
|---------|-------------|---------|
| Milestone shape | Diamond / Circle / Square / Triangle / Star | Diamond |
| Milestone color | Fill color | #c4314b |
| Milestone size | Size in pixels (6–24 px) | 12 |

---

### 7. Top level timeline

A grand-summary "All" row that rolls every task into one bar (or one bar per category) above the main chart. Has its own card-level toggle.

#### Top level Group

| Setting | Description | Default |
|---------|-------------|---------|
| Breakdown | Single bar OR segmented by category | Single bar |
| Include milestones | Show milestone markers on the summary row | On |
| Header label | Label shown next to the top-level row | All |
| Show task count | Append `(n)` task count after the header label | On |

#### Bar Group

| Setting | Description | Default |
|---------|-------------|---------|
| Color | Default bar color | #9E9E9E |
| Use category colors | When breakdown is "by category", color each segment with the category's first task color | On |
| Opacity (%) | Bar transparency (10–100) | 100 |
| Height (%) | Bar height as a percentage of row height (20–100) | 60 |
| Corner radius | Rounded corners (0–12 px) | 2 |
| Row height (%) | Row height as a percentage of the default row height (50–500) | 100 |

#### Label Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show (group toggle) | Show the duration label on the summary bar | On |
| Font | Font family, size (6–24), bold, italic, underline | Segoe UI, 10pt, Bold |
| Color | Label text color | #ffffff |
| Auto contrast | Pick black or white to contrast with the bar color | On |
| Unit | Duration unit shown in the label (Days / Weeks / Months) | Days |

---

### 8. Category timeline

Summary bars per category (driven by the Category data field). Card-level toggle controls whether the category rows appear at all.

#### Category Group

| Setting | Description | Default |
|---------|-------------|---------|
| Font | Font family, size (10–24), bold, italic, underline | Segoe UI, 13pt, Bold |
| Color | Category header text color | #424242 |
| Expanded by default | Categories start in expanded state | On |
| Include milestones | Show milestone markers on category summary rows | On |

#### Bar Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show (group toggle) | Show the per-category summary bar | On |
| Color | Default category bar color | #9E9E9E |
| Use category colors | Color each summary bar with the category's first task color | Off |
| Opacity (%) | Bar transparency (10–100) | 100 |
| Height (%) | Bar height as a percentage of row height (20–100) | 60 |
| Corner radius | Rounded corners (0–12 px) | 2 |
| Row height (%) | Row height as a percentage of the default row height (50–500) | 100 |

#### Label Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show (group toggle) | Show the duration label on the per-category summary bar | On |
| Font | Font family, size (6–24), bold, italic, underline | Segoe UI, 10pt, Bold |
| Color | Label text color | #ffffff |
| Auto contrast | Pick black or white to contrast with the bar color | On |

---

### 9. Markers

Vertical marker lines for the today line and any custom Marker Date measures you bind.

#### Appearance Group

| Setting | Description | Default |
|---------|-------------|---------|
| Color | Marker line color (applies to today and custom markers) | #c4314b |
| Width | Line thickness (1–6 px) | 2 |
| Style | Solid / Dashed / Dotted | Solid |

#### Today Group

| Setting | Description | Default |
|---------|-------------|---------|
| Today | Display today marker line | On |
| Label | Display label above the marker line | On |
| Label text | Custom text for the marker label | Today |
| Day offset | Shift marker forward or back by days (-365 to 365) | 0 |

*Tip: Use Day offset to show a deadline or milestone date relative to today. Positive values move the marker into the future, negative values into the past.*

---

### 10. Analytics

Dependency arrows plus the three analytics features (Critical path, Slippage, Resource conflicts), each with its own canvas toggle button.

#### Dependencies Group

| Setting | Description | Default |
|---------|-------------|---------|
| Dependency lines | Show task connection arrows | On |
| Color | Line color | #616161 |
| Width | Line thickness (1–5 px) | 1 |
| Style | Solid / Dashed / Dotted | Solid |
| Path | Curved / Straight (elbow) / Straight down | Straight down |
| Arrow size | Size of arrowhead (4–16 px) | 8 |

#### Critical path Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show toggle button | Show the Critical Path toggle button on the visual | On |
| Critical path color | Highlight border color for critical path tasks | #c4314b |
| Border width | Highlight border thickness (1–6 px) | 2 |
| Duration summary | Display critical path duration stats at bottom of chart | On |

*The toggle is automatically hidden when the data has no Dependencies, since critical path requires dependency information.*

#### Slippage Group

| Setting | Description | Default |
|---------|-------------|---------|
| Show toggle button | Show the Slippage toggle button on the visual | On |
| Slipped color | Color used for tasks that have been pushed past their original dates | #c4314b |

*The Slippage toggle controls both highlighting **and** date cascading. When OFF (default), tasks render at their user-specified Start/End dates. When ON, tasks with Dependencies are pushed forward so they start the day after the latest predecessor ends, and tasks that moved are highlighted in the slipped color. The toggle is automatically hidden when the data has no Dependencies.*

#### Resource conflicts Group

| Setting | Description | Default |
|---------|-------------|---------|
| Highlight conflicts | Detect and highlight tasks where the same resource is double-booked | On |
| Highlight color | Pill background color used on conflicting resource cells | #d83b01 |
| Border width | Reserved for future styling (1–6 px) | 2 |
| Show toggle button | Show the Resource conflicts toggle button on the visual | On |

*When detection is on, any two non-milestone tasks that share a resource (case-insensitive; comma-separated values are split) AND overlap in time get a colored pill on the resource cell. Hover the cell to see which other tasks are in conflict. Click a resource cell to focus that resource — rows whose tasks don't include it are dimmed; click empty chart space to clear.*

## Version History

### Version 2.7.0.0

**Format pane cleanup and UX:**

- **Time scale** is now an **Auto time scale** toggle (default On). When On, the Primary unit / Secondary unit / Week starts on / Day unit min width controls are hidden. Turn Off to configure units manually.
- The two **Units** groups in the Axis card are now context-aware: when Start/End columns are dates, the Relative units group is **disabled** (greyed out with a hover reason). When Start/End are numeric (relative mode), the standard Units group is disabled. Both stay visible so the user can see what's available.
- Removed conditional-formatting (fx) buttons from every color/numeric control in the format pane. The previous fx-on-everything was noisy and the persistence model didn't fit a table dataView. Per-category coloring will return in a future release.
- **Category timeline** card cleaned up: Bar group adds Show toggle, opacity, height, corner radius, row height, and an option to color the summary bar with the first task's color. New **Label** subgroup splits font/color/auto-contrast away from the bar settings.
- **Top level timeline** card: Label subgroup split out from the bar settings; the bar group adds row-height controls.
- **Layout positions** card: new **Zoom controls** group with a Show toggle to hide the zoom +/- buttons.
- **Resource conflicts** toggle on the canvas now widens to fit and shows a count pill summary when there are conflicts.
- Removed the redundant "Task" header line from the bar tooltip.

### Version 2.6.0.0

**Resource awareness, on-demand slippage, and bundled samples:**

- Added **Resource** data field with dedicated column rendering
- Added **Resource conflict** detection: tasks sharing a resource with overlapping dates display a colored pill on the resource cell, and a tooltip lists the conflicting task names
- Added **Resource conflicts toggle** button on the canvas (joins Critical Path and Slippage toggles)
- Click a resource cell to **focus that resource** — rows whose tasks don't include the resource are dimmed; click again or click empty chart space to clear
- **Slippage toggle now controls date cascading**: when OFF (default), tasks render at their user-specified dates. When ON, dependent tasks are pushed forward by their predecessors and the moved tasks are highlighted
- **Critical Path and Slippage toggles are auto-hidden** when the dataset has no Dependencies (since both require dependency information)
- **Relative-units mode**: Start/End now accept numeric values (with a configurable origin) so the visual can render schedules measured in hours, minutes, days, etc., instead of calendar dates. Duration labels everywhere honor the unit suffix (h, min, d, w, mo, y, s)
- Added marker measures and pre-built **TMDL sample datasets** (`Calendar_ProductLaunch.tmdl`, `RelativeUnits_LaunchDay.tmdl`) under `assets/sample-data/` that demonstrate critical path, slippage, conflicts, milestones, dependencies, categories, and resources end-to-end

**Format pane overhaul:**

- Pane reorganized into **10 top-level cards** in display order: Style presets, Layout, Axis, Columns, Bars, Milestones, Top level timeline, Category timeline, Markers, Analytics
- New **Layout** card with a Position group for axis / task column / context columns / resource column placement (left, right, top, bottom)
- New **Axis** card consolidates Units, Relative units, Axis title, Primary lines, Secondary lines, Divider, Row shading, and Day shading into one composite card
- New **Columns** card groups Task column, Context columns, and the new Resource column together
- **Milestones** promoted from a Bars subgroup to its own top-level card
- **Timeline** split into **Top level timeline** (grand-summary "All" row) and **Category timeline** (per-category summary rows), each with its own card-level toggle
- Old **Connections** card renamed to **Analytics** and now contains Dependencies, Critical path, Slippage, and the new Resource conflicts groups — each analytics feature has its own canvas toggle slice

### Version 2.5.0.0

**Flexible Time Scale:**

- Added Time Scale mode setting (Auto/Manual) in Date Axis settings
- Auto mode intelligently selects the best time unit based on date range
- Manual mode lets you specify Primary unit (Day, Week, Month, Quarter, Year)
- Added Secondary unit option for two-tier date axis hierarchy (e.g., Months grouped under Years)
- Secondary tier displays grouping labels with bracket lines above/below primary labels
- Renamed grid line settings to Primary Lines (at primary unit intervals) and Secondary Lines (at secondary unit boundaries)
- Primary and Secondary lines now have independent show/hide, color, and style settings
- Improved date alignment to respect unit boundaries (weeks start Monday, months start 1st, etc.)
- Added "Week starts on" setting to configure which day begins the week (Sunday, Monday, etc.)

### Version 2.4.0.0

**Context Column Filtering:**

- Added Context Columns data field for displaying additional task attributes (Status, Owner, Priority, etc.)
- Click any context column header with ▾ to open a multi-select filter popup
- Fluent 2 styled popup with checkboxes for each unique value
- Support for filtering by blank/empty values (shown as "(Blank)")
- Select All / Clear All quick actions
- Header shows filter status (turns blue when filtered, displays selected count or single value)
- Apply button to confirm selections, click outside to cancel
- Filter popup stays within visual bounds (Power BI custom visual limitation)

### Version 2.2.1.0

**High Contrast Mode Enhancements:**

- Landing page now uses high contrast colors when HC mode is active

### Version 2.2.0.0

- Added auto-contrast for duration labels (automatically adjusts text color based on bar color for better visibility)
- Added category summary bar tooltip showing task count, start/end dates, and total duration
- Added tooltip headers to distinguish between Task, Milestone, and Category Summary tooltips
- Added hover tooltips on task labels and category labels to show full names (useful for truncated text)
- Simplified style preset logic for more stable rendering during resize and toggle interactions
- Fixed preset switching issue when using on-visual toggles (Critical Path, Slippage)
- Removed auto-contrast from task labels (labels are on row background, not bars)
- Various stability improvements

### Version 2.3.0.0

- Renamed style presets to Default, Comfortable, Relaxed, Spacious (removed Custom option)
- Changed default preset to compact sizing (bar height 14px, spacing 2px, corner radius 4px)
- Reduced default task label font size from 12pt to 10pt for better information density
- Improved preset behavior: presets now apply values only when changed, allowing subsequent manual adjustments
- Fixed "reset to default" behavior to correctly restore default preset values

### Version 2.1.0.0

- Added style presets (Default, Compact, Very Compact, Spacious)
- Added slippage toggle button with summary display
- Added progress format option (whole number vs percentage)
- Added conditional formatting support for all numeric and color options
- Updated localization for all new features

### Version 2.0.2.0

- Added Progress % field for task completion tracking
- Added Marker Dates field for custom vertical marker lines (supports multiple measures)
- Added Today Line with configurable offset, style, and label
- Added task label max width and word wrap options
- Improved label truncation with configurable width

### Version 2.0.0.0

- Added localization support (EN, ES, FR, DE, PT-BR)
- Added rendering events for certification
- Added multi-visual selection support
- Added keyboard navigation
- Added high-contrast mode support
- Added landing page
- Added context menu support
- Added critical path toggle button
- Enhanced accessibility features

### Version 1.0.0.0

- Initial release
- Basic Gantt chart functionality
- Dependency arrows
- Critical path calculation
- Category grouping
- Milestone support

## Support

For issues, feature requests, or questions:

- **Website**: <https://datazoepowerbi.com>
- **Email**: <zoe@datazoepowerbi.com>

## Acknowledgments

This visual and documentation were created with the assistance of GitHub Copilot.

## License

MIT License - See LICENSE file for details.
