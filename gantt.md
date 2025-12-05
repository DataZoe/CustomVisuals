# Gantt Chart Visual for Power BI

A powerful, feature-rich Gantt chart custom visual for Microsoft Power BI that helps you visualize project timelines, track task dependencies, and identify critical paths.

![Gantt Chart Visual](assets/gantt-icon.png)

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

### 📁 Category Grouping
Organize tasks into collapsible categories for better organization of large projects. Summary bars show the span of each category.

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
| **Start Date** | ✅ Yes | When the task begins |
| **End Date** | Optional | When the task ends. If empty, task appears as a milestone |
| **Category** | Optional | Groups tasks into collapsible sections |
| **Task ID** | Optional | Unique identifier for dependency linking |
| **Dependencies** | Optional | Comma-separated Task IDs that must complete first |
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
- A column for start dates

Optionally include:
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

### Step 4: Customize Appearance
1. With the visual selected, click the **Format** pane (paint roller icon)
2. Expand the formatting cards to customize:
   - **Task bars**: Colors, borders, opacity, height
   - **Milestones**: Shape, color, size
   - **Critical path**: Enable/disable, colors
   - **Task labels**: Font size, color
   - **Grid lines**: Show/hide, color
   - **Date header**: Font settings
   - **Categories**: Header color, expand/collapse behavior

### Step 5: Interact with the Chart
- **Click** a task to select it and cross-filter other visuals
- **Ctrl+Click** to select multiple tasks
- **Click** category headers to expand/collapse groups
- **Use the Critical Path toggle** button to show/hide the critical path
- **Right-click** for context menu options
- **Use Tab/Arrow keys** for keyboard navigation

## Example: Software Development Project

### Sample Data

Copy this data into Excel or create it in Power BI:

| TaskID | Category | Task | StartDate | EndDate | Dependencies |
|--------|----------|------|-----------|---------|--------------|
| 1 | Planning | Project Kickoff | 2025-01-06 | 2025-01-06 | |
| 2 | Planning | Requirements Gathering | 2025-01-07 | 2025-01-17 | 1 |
| 3 | Planning | Technical Specification | 2025-01-13 | 2025-01-24 | 2 |
| 4 | Planning | Architecture Review | 2025-01-27 | 2025-01-27 | 3 |
| 5 | Development | Database Design | 2025-01-28 | 2025-02-07 | 4 |
| 6 | Development | API Development | 2025-02-03 | 2025-02-21 | 5 |
| 7 | Development | Frontend Development | 2025-02-10 | 2025-02-28 | 5 |
| 8 | Development | Integration | 2025-02-24 | 2025-03-07 | 6, 7 |
| 9 | Testing | Unit Testing | 2025-02-17 | 2025-03-07 | 6 |
| 10 | Testing | Integration Testing | 2025-03-10 | 2025-03-21 | 8, 9 |
| 11 | Testing | User Acceptance Testing | 2025-03-24 | 2025-04-04 | 10 |
| 12 | Deployment | Production Deployment | 2025-04-07 | 2025-04-11 | 11 |
| 13 | Deployment | Go Live | 2025-04-14 | 2025-04-14 | 12 |

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

4. **Observe the results:**
   - Tasks are grouped by category (Planning, Development, Testing, Deployment)
   - Milestones (Project Kickoff, Architecture Review, Go Live) appear as diamonds
   - Dependency arrows connect related tasks
   - The critical path is highlighted

5. **Toggle the Critical Path:**
   - Click the "Critical Path" toggle button in the chart header
   - Tasks on the critical path are highlighted with a colored border
   - The summary shows total critical path duration

6. **Explore the categories:**
   - Click the ▼ arrow next to "Development" to collapse that section
   - Click again to expand
   - Notice the summary bar showing the category's time span

## Example: Marketing Campaign

### Sample Data

| TaskID | Category | Task | StartDate | EndDate | Dependencies |
|--------|----------|------|-----------|---------|--------------|
| M1 | Strategy | Campaign Brief | 2025-02-03 | 2025-02-07 | |
| M2 | Strategy | Target Audience Research | 2025-02-10 | 2025-02-14 | M1 |
| M3 | Strategy | Budget Approval | 2025-02-17 | 2025-02-17 | M2 |
| M4 | Creative | Concept Development | 2025-02-18 | 2025-02-28 | M3 |
| M5 | Creative | Copywriting | 2025-02-24 | 2025-03-07 | M4 |
| M6 | Creative | Design Assets | 2025-02-24 | 2025-03-14 | M4 |
| M7 | Creative | Video Production | 2025-03-03 | 2025-03-21 | M4 |
| M8 | Digital | Landing Page | 2025-03-10 | 2025-03-21 | M5, M6 |
| M9 | Digital | Email Templates | 2025-03-10 | 2025-03-17 | M5 |
| M10 | Digital | Social Media Setup | 2025-03-17 | 2025-03-21 | M6 |
| M11 | Launch | Soft Launch | 2025-03-24 | 2025-03-28 | M8, M9, M10, M7 |
| M12 | Launch | Full Campaign Launch | 2025-03-31 | 2025-03-31 | M11 |
| M13 | Launch | Performance Review | 2025-04-14 | 2025-04-18 | M12 |

### Key Observations

- **M3 (Budget Approval)** and **M12 (Full Campaign Launch)** are milestones
- **Creative** tasks can run in parallel after Concept Development
- The critical path likely runs through the longest creative task (Video Production)
- **Soft Launch** depends on multiple tasks completing

## Example: Construction Project

### Sample Data

| TaskID | Category | Task | StartDate | EndDate | Dependencies |
|--------|----------|------|-----------|---------|--------------|
| C1 | Permits | Site Survey | 2025-03-03 | 2025-03-14 | |
| C2 | Permits | Permit Application | 2025-03-17 | 2025-03-28 | C1 |
| C3 | Permits | Permit Approved | 2025-04-14 | 2025-04-14 | C2 |
| C4 | Foundation | Excavation | 2025-04-15 | 2025-04-25 | C3 |
| C5 | Foundation | Foundation Pour | 2025-04-28 | 2025-05-02 | C4 |
| C6 | Foundation | Curing Period | 2025-05-05 | 2025-05-16 | C5 |
| C7 | Structure | Framing | 2025-05-19 | 2025-06-13 | C6 |
| C8 | Structure | Roofing | 2025-06-16 | 2025-06-27 | C7 |
| C9 | Structure | Windows & Doors | 2025-06-23 | 2025-07-03 | C7 |
| C10 | Systems | Electrical Rough-in | 2025-06-30 | 2025-07-18 | C8 |
| C11 | Systems | Plumbing Rough-in | 2025-06-30 | 2025-07-18 | C8 |
| C12 | Systems | HVAC Installation | 2025-07-07 | 2025-07-25 | C8 |
| C13 | Interior | Insulation | 2025-07-21 | 2025-07-30 | C10, C11 |
| C14 | Interior | Drywall | 2025-08-01 | 2025-08-15 | C13 |
| C15 | Interior | Painting | 2025-08-18 | 2025-08-29 | C14 |
| C16 | Interior | Flooring | 2025-09-01 | 2025-09-12 | C15 |
| C17 | Finishing | Fixtures & Appliances | 2025-09-15 | 2025-09-26 | C16, C12 |
| C18 | Finishing | Final Inspection | 2025-09-29 | 2025-09-29 | C17 |
| C19 | Finishing | Certificate of Occupancy | 2025-10-06 | 2025-10-06 | C18 |

### Key Features Demonstrated

- **Long dependency chains** show the sequential nature of construction
- **Parallel work** in the Systems phase (Electrical, Plumbing, HVAC)
- **Milestone dates** for permit approval, inspection, and certificate
- **Critical path** identifies which delays would impact completion

## Tips and Best Practices

### Data Preparation
- Use consistent date formats
- Keep Task IDs unique and simple (numbers or short codes)
- Use comma-separated values for multiple dependencies
- Leave End Date empty for milestones

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

### Task Bars
| Setting | Description | Default |
|---------|-------------|---------|
| Show | Display task bars | On |
| Use theme color palette | Auto-assign colors by category | Off |
| Fill color | Bar fill color | #0078D4 |
| Opacity | Bar transparency (0-100%) | 100% |
| Show border | Display bar border | Off |
| Border color | Border color | #005A9E |
| Border width | Border thickness (px) | 1 |
| Bar height | Height of bars (px) | 20 |
| Corner radius | Rounded corners (px) | 4 |
| Row spacing | Space between rows (px) | 8 |
| Show duration on bars | Display duration text | Off |
| Highlight slipped tasks | Color tasks pushed by dependencies | On |
| Slipped color | Color for slipped tasks | #FFA500 |

### Milestones
| Setting | Description | Default |
|---------|-------------|---------|
| Show | Display milestones | On |
| Shape | Diamond or circle | Diamond |
| Color | Milestone fill color | #D83B01 |
| Size | Milestone size (px) | 12 |

### Critical Path
| Setting | Description | Default |
|---------|-------------|---------|
| Show | Highlight critical path | On |
| Color | Critical path border color | #D13438 |
| Border width | Critical path border (px) | 3 |
| Show summary | Display critical path stats | On |

## Version History

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
- **Website**: https://datazoepowerbi.com
- **Email**: zoe@datazoepowerbi.com

## License

MIT License - See LICENSE file for details.
