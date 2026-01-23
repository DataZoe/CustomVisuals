# DataZoe Word Cloud

A beautiful, modern word cloud visualization for Power BI with Fluent 2 design system styling.

## Why Use This Visual?

### Make Your Data Memorable
Transform boring lists and categories into eye-catching word clouds that instantly communicate what matters most. Large words grab attention, making it easy for report viewers to identify top performers, trending topics, or key themes at a glance.

### Match Your Brand
Choose from 9 color schemes including your report theme colors, or extract colors directly from your company logo or brand image. Your word clouds will look like they belong in your reports, not like an afterthought.

### Keep It Clean
Built with Microsoft's Fluent 2 design language, this visual looks polished and professional. Subtle shadows, smooth animations, and modern typography ensure your reports feel cohesive and up-to-date.

### Works for Everyone
Full accessibility support means all your report users can interact with the visual—keyboard navigation, screen reader support, and high contrast mode are built in, not bolted on.

### Tell a Richer Story
Add tooltips to show additional context when users hover over words. Connect your word cloud to other visuals with cross-filtering so clicking a word updates your entire report.

## Example Data

Here's sample data showing product feedback categories and their mention counts:

| Feedback Topic | Mentions | Sentiment Score |
|----------------|----------|-----------------|
| Easy to use | 847 | 4.8 |
| Fast delivery | 623 | 4.6 |
| Great value | 589 | 4.5 |
| Quality product | 534 | 4.7 |
| Helpful support | 412 | 4.4 |
| Good packaging | 387 | 4.2 |
| Clear instructions | 298 | 4.1 |
| Durable | 276 | 4.3 |
| Lightweight | 234 | 4.0 |
| Stylish design | 198 | 4.2 |
| Eco friendly | 167 | 4.5 |
| Quick setup | 145 | 4.3 |
| Compact size | 132 | 3.9 |
| Long battery | 98 | 4.1 |
| Quiet operation | 87 | 4.0 |

### DAX Table Example

Create this sample data directly in Power BI using DAX:

```dax
Feedback Data = 
SELECTCOLUMNS(
    {
        ("Easy to use", 847, 4.8),
        ("Fast delivery", 623, 4.6),
        ("Great value", 589, 4.5),
        ("Quality product", 534, 4.7),
        ("Helpful support", 412, 4.4),
        ("Good packaging", 387, 4.2),
        ("Clear instructions", 298, 4.1),
        ("Durable", 276, 4.3),
        ("Lightweight", 234, 4.0),
        ("Stylish design", 198, 4.2),
        ("Eco friendly", 167, 4.5),
        ("Quick setup", 145, 4.3),
        ("Compact size", 132, 3.9),
        ("Long battery", 98, 4.1),
        ("Quiet operation", 87, 4.0)
    },
    "Feedback Topic", [Value1],
    "Mentions", [Value2],
    "Sentiment Score", [Value3]
)
```

Then drag **Feedback Topic** to Words, **Mentions** to Values, and **Sentiment Score** to Tooltips.

---

## Example 2: Skills & Expertise

Visualize team skills or job requirements with weighted proficiency levels:

| Skill | Proficiency | Team Members |
|-------|-------------|--------------|
| Python | 95 | 12 |
| SQL | 92 | 15 |
| Power BI | 88 | 10 |
| Excel | 85 | 18 |
| Data Analysis | 82 | 14 |
| Machine Learning | 78 | 6 |
| Azure | 75 | 8 |
| Tableau | 70 | 5 |
| R | 68 | 4 |
| JavaScript | 65 | 7 |
| Spark | 60 | 3 |
| Docker | 55 | 4 |
| Kubernetes | 50 | 2 |

### DAX Table Example

```dax
Skills Data = 
SELECTCOLUMNS(
    {
        ("Python", 95, 12),
        ("SQL", 92, 15),
        ("Power BI", 88, 10),
        ("Excel", 85, 18),
        ("Data Analysis", 82, 14),
        ("Machine Learning", 78, 6),
        ("Azure", 75, 8),
        ("Tableau", 70, 5),
        ("R", 68, 4),
        ("JavaScript", 65, 7),
        ("Spark", 60, 3),
        ("Docker", 55, 4),
        ("Kubernetes", 50, 2)
    },
    "Skill", [Value1],
    "Proficiency", [Value2],
    "Team Members", [Value3]
)
```

Then drag **Skill** to Words, **Proficiency** to Values, and **Team Members** to Tooltips.

---

## Data Fields

| Field | Type | Description |
|-------|------|-------------|
| Words | Category | Text field containing the words to display |
| Values | Measure | Numeric value determining word size |
| Tooltips | Measure | Additional measures to show in tooltips (up to 5) |

## Getting Started

1. Add the visual to your report
2. Drag a text/category field to the **Words** bucket
3. Drag a measure to the **Values** bucket to size words by importance
4. Customize the appearance in the format pane

## Format Options

### Text
- Minimum and maximum font sizes
- Font family selection

### Layout
- Layout type (Archimedean, Rectangular, Compact, Centered, Random scatter)
- Rotation style (Horizontal, Vertical, Mixed, Diagonal, Slight, Angled, Any angle)
- Word spacing
- Maximum words to display

### Split Text
- Break phrases into individual words
- Custom delimiters
- Minimum word length filter
- Exclude specific words

### Colors
- 9 color schemes (Report theme, Fluent 2, Brand blue, Cool/Warm tones, Rainbow, Monochrome, From image, Custom)
- Extract colors from images via base64 data URI
- Define custom 5-color palettes

### Animation
- Enable/disable animations
- Animation duration
- Hover scale effect

### Plot Area Background
- Background color (supports transparent)
- Corner radius and padding
- Border styling
- Shadow effect

## Accessibility

- Full keyboard navigation (Tab, Enter, Space, Escape)
- High contrast mode support
- ARIA labels for screen readers
- Automatic color contrast adjustment

## Supported Languages

English, German, Spanish, French, Japanese, Portuguese (Brazil), Chinese (Simplified)

## Version History

### 1.0.4.0
- Improved responsive scaling - word cloud now fills the visual better when resized
- Added toggle to show/hide extracted colors

### 1.0.3.0
- Reorganized format pane (Text, Layout, Split text cards)
- Added transparent background support
- Added toggle to show/hide extracted colors
- Renamed Appearance to Plot area background

### 1.0.2.0
- Added localization support (7 languages)
- Added keyboard navigation and accessibility features
- Added context menu support
- Updated documentation

### 1.0.1.0
- Added "From image" color extraction
- Added phrase splitting and word filtering
- Added Report Theme color scheme
- Added more layout and rotation options

### 1.0.0.0
- Initial release
