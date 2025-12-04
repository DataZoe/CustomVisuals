# Gradient Card Custom Visual for Power BI

## 1. What It Is

The **Gradient Card** is a custom Power BI visual that displays key metrics as visually appealing cards with customizable gradient backgrounds. It supports single cards or small multiples (multiple cards in a grid layout), making it ideal for KPI dashboards, scorecards, and executive summaries. Each card can display a primary value, comparison/target value, progress bar, badge indicator, and optional icon.

**Inspiration:** This visual was inspired by [Charles Edward's SVG card concept](https://www.linkedin.com/posts/edward-charles-085025b1_last-weekend-i-spoke-with-adrian-liu-about-activity-7400397799328083968-l04h). Thank you Charles for sharing your creative approach!

---

## 2. Key Benefits

- **Visual Impact** – Gradient backgrounds and customizable styling create professional, eye-catching KPI displays
- **At-a-Glance Insights** – Combines value, target, progress, and status in a single compact visualization
- **Flexible Data Binding** – Supports field parameters, allowing dynamic switching between metrics
- **Small Multiples** – Automatically generates multiple cards from categories or multiple measures
- **Fully Accessible** – High-contrast mode support and keyboard navigation for accessibility compliance
- **Highly Customizable** – Extensive formatting options for colors, fonts, sizes, and layout
- **Interactive** – Supports selection, cross-filtering, drill-through, and tooltips

---

## 3. Features

### Data Roles

| Field | Description |
|-------|-------------|
| **Primary** | The main metric value displayed prominently on the card |
| **Comparison** | Target/comparison value for progress calculation and display |
| **Category** | Groups data into multiple cards (small multiples) |
| **Icon** | Data-driven icon field for dynamic icons per card |
| **Tooltips** | Additional measures to display in tooltips |

### Card Layout & Styling

- **Gradient Background** – Two-color gradient with customizable angle (0-360°)
- **Border Radius** – Rounded corners (adjustable)
- **Card Border** – Optional border with customizable width, color, and style (solid, dashed, dotted)
- **Padding & Spacing** – Control internal spacing between elements
- **Small Multiples Grid** – Automatic responsive grid layout with configurable minimum card width and padding

### Title Section

- Show/hide title
- Custom title text (or auto-generated from data)
- Font customization (family, size, color, bold, italic)

### Badge Indicator

- Displays percentage of target achieved
- **Three-Tier Conditional Coloring** – Matches progress bar colors for below/above marker/100%
- Customizable background, border, font, and padding
- Adjustable fill lightness for background tint

### Main Value Display

- Large, prominent metric display
- Display units (Auto, None, Thousands, Millions, Billions, Trillions)
- Decimal places control
- Thousands separator toggle
- Full font customization

### Icon Support

- **12 Built-in Icons**: Star, Heart, Checkmark, Trophy, Target, Chart, Dollar, Users, Thumbs Up, Lightning, Fire, Rocket
- **Custom Image URL** – Use any image via URL
- **Data-Driven Icons** – Bind icon selection to a data field
- Customizable size, color, spacing, and border radius

### Details Section (Target/Comparison)

- Shows "Target: [value]" and variance when comparison data exists
- **Three-Tier Variance Labels**:
  - "To go:" when below target % marker
  - "Exceeded:" when at/above target % marker but below 100%
  - "Achieved:" when actual ≥ target (100%)
- Customizable labels for each state
- Show/hide +/- sign on variance values
- Separate colors for labels, values, and exceeded amounts
- Optional color matching with progress bar (three-tier colors)
- Separator styling

### Progress Bar

- Visual progress indicator comparing actual vs. target
- **Data-Driven Mode** – Automatically calculates from Primary and Comparison fields
- **Manual Mode** – Set fixed max value and marker position
- **Three-Tier Color System**:
  - Color when below target % marker
  - Color when at/above target % marker (but below 100%)
  - Color when at/above 100% (actual ≥ target)
- Customizable marker (position, color, width, height) – auto-hides when > 100%
- Progress label with percentage display
- Adjustable bar height and border radius

### Tooltips

- Standard Power BI tooltips with custom tooltip fields
- Canvas (report page) tooltips supported
- Configurable tooltip trigger zones:
  - Primary value
  - Icon
  - Header/title
  - Badge
  - Comparison section
  - Progress bar
  - Anywhere on card

### Interactivity

- **Selection** – Click to select/filter; Ctrl+click for multi-select
- **Cross-Filtering** – Selections filter other visuals
- **Drill-Through** – Right-click context menu for drill-through pages
- **Keyboard Navigation** – Tab between cards, Enter/Space to select, Esc to exit

### Accessibility

- **High-Contrast Mode** – Automatically adapts colors for Windows high-contrast themes
- **Keyboard Focus** – Full keyboard navigation support with visible focus indicators
- **Screen Reader Compatible** – Proper element structure

### Field Parameter Support

- Use field parameters in Primary and/or Comparison fields
- Automatically expands to multiple cards based on parameter selections
- When Primary has fewer measures than Comparison, Primary value repeats across cards

---

## 4. Recommended Use Cases

### Executive Dashboards

Display top-level KPIs (Revenue, Profit, Customer Count) with gradient styling that matches corporate branding. Progress bars show performance against targets at a glance.

### Sales Scorecards

Show individual salesperson or region performance with small multiples. Each card displays actual sales, target, and % achieved with conditional coloring.

### Financial Reporting

Present budget vs. actual metrics with exceeded amounts highlighted. Use icons to categorize expense types or departments.

### Operational Metrics

Monitor production, quality, or service metrics with progress indicators. Color coding immediately shows which KPIs need attention.

### Goal Tracking

Track progress toward quarterly or annual goals. The progress bar and badge provide instant visual feedback on achievement status.

### Dynamic Metric Selection

Use field parameters to let users switch between different metrics (e.g., Revenue/Units/Margin) without creating multiple visuals.

### Marketing Dashboards

Display campaign performance metrics with custom icons representing different channels. Tooltips provide detailed breakdowns.

### HR Analytics

Show headcount, turnover, satisfaction scores with department categories creating a grid of cards for easy comparison.

---

## 5. Step-by-Step Setup Guide

### Step 1: Import the Visual

1. Download the `.pbiviz` file (e.g., `gradientCard.1.2.4.0.pbiviz`)
2. In Power BI Desktop, go to **Home** → **Get Visuals** → **Import a visual from a file**
3. Select the `.pbiviz` file and click **Open**
4. Click **Import** when prompted
5. The Gradient Card icon will appear in your Visualizations pane

### Step 2: Add the Visual to Your Report

1. Click the **Gradient Card** icon in the Visualizations pane
2. A blank visual placeholder will appear on your canvas
3. Resize and position the visual as needed

### Step 3: Add Your Primary Metric

1. In the Fields pane, find your main measure (e.g., "Total Sales")
2. Drag it to the **Primary** field well
3. The card will display your metric value

### Step 4: Add a Target/Comparison Value (Optional)

1. Drag a target or comparison measure to the **Comparison** field well
2. The card will now show:
   - Target value in the details section
   - "Exceeded" amount (actual minus target)
   - Progress bar (if enabled) showing % of target

### Step 5: Create Small Multiples (Optional)

**Option A: Using a Category Field**

1. Drag a dimension (e.g., "Region", "Product") to the **Category** field
2. Multiple cards will appear, one for each category value

**Option B: Using Multiple Measures**

1. Add multiple measures to **Primary** (e.g., Revenue, Units, Margin)
2. Each measure will display as a separate card

**Option C: Using Field Parameters**

1. Create a field parameter in Power BI (Modeling → New Parameter → Fields)
2. Add the field parameter to **Primary** or **Comparison**
3. Use a slicer to let users select which metrics to display

### Step 6: Configure the Progress Bar

1. Open the Format pane (paint roller icon)
2. Expand **Progress Bar**
3. Toggle **Show** to On
4. Configure settings:
   - **Bar Color Below Marker**: Color when below target % marker
   - **Bar Color**: Color when at/above target % marker
   - **Bar Color at 100%**: Color when actual ≥ target (default green)
   - **Show Marker**: Toggle the target line (auto-hides if > 100%)
   - **Show Label**: Display percentage text

### Step 7: Customize the Appearance

**General Settings:**

- Set gradient colors (Color 1, Color 2)
- Adjust gradient angle
- Set border radius and padding

**Title Settings:**

- Show/hide title
- Set custom text or use data-driven title
- Customize font family, size, color, bold/italic

**Badge Settings:**

- Show/hide the percentage badge
- Enable "Match Progress Colors" for conditional coloring
- Customize badge appearance

**Main Value Settings:**

- Set font family, size, color
- Configure display units (K, M, B, T)
- Set decimal places

**Icon Settings:**

- Toggle icon on/off
- Select a built-in icon or enter a custom image URL
- Adjust size, color, and spacing

**Details Settings:**

- Show/hide target and exceeded values
- Customize labels (e.g., "Goal" instead of "Target")
- Enable conditional coloring

### Step 8: Configure Tooltips (Optional)

1. Drag additional measures to the **Tooltips** field well
2. In Format pane → **Tooltips**:
   - Toggle which elements show tooltips
   - Enable "Show Anywhere" to trigger on any card area
   - Enable "Show Only Tooltip Fields" to hide default values

### Step 9: Add an Icon (Optional)

**Static Icon:**

1. Format pane → **Icon** → Show: On
2. Select a built-in icon from the dropdown
3. Or enter a custom image URL

**Data-Driven Icon:**

1. Create a column in your data with icon names (e.g., "star", "trophy")
2. Drag that field to the **Icon** field well
3. The icon will change based on your data

### Step 10: Adjust Small Multiples Layout

1. Format pane → **Small Multiples**
2. Set **Minimum Card Width** (default: 200px)
3. Set **Padding** between cards (default: 10px)
4. Cards will automatically arrange in a responsive grid

---

## 6. Quick Start Examples

### Example 1: Simple KPI Card

- **Primary**: Total Revenue measure
- **Format**: Choose gradient colors, set display units to "Millions"

### Example 2: KPI with Target

- **Primary**: Actual Sales
- **Comparison**: Target Sales
- **Progress Bar**: Enable, set colors for above/below target

### Example 3: Regional Scorecard

- **Primary**: Revenue
- **Comparison**: Target
- **Category**: Region
- Result: One card per region showing performance

### Example 4: Dynamic Metric Selector

- Create a field parameter with Revenue, Profit, Units
- **Primary**: Field parameter
- Add slicer for the parameter
- Users can toggle between metrics

---

## 7. Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.2.4.0 | Dec 2025 | High-contrast mode, keyboard navigation, three-tier progress system (below marker/above marker/100%), card border options, customizable variance labels |
| 1.2.3.0 | Dec 2025 | Field parameter support for Primary and Comparison fields |

---

**Author:** Zoe Douglas  
**Support:** https://datazoepowerbi.com
