# DataZoe Word Cloud

A beautiful, modern word cloud visualization for Power BI with Fluent 2 design system styling.

## Features

### Fluent 2 Design
- Clean, modern aesthetic following Microsoft's Fluent 2 design language
- Smooth animations and hover effects
- Subtle shadows and rounded corners
- High contrast mode support for accessibility
- Keyboard navigation support

### Color Schemes
- **Report Theme** - Uses your report's theme colors
- **Fluent 2** - Official Fluent 2 color palette
- **Brand Blue** - Microsoft brand colors
- **Cool Tones** - Blues, greens, and purples
- **Warm Tones** - Oranges, reds, and yellows
- **Rainbow** - Full spectrum colors
- **Monochrome** - Grayscale palette
- **From Image** - Extract colors from a base64 image
- **Custom** - Define your own 5 colors

### Word Layout Options
- **Layout Types**: Archimedean, Rectangular, Compact, Centered, or Random scatter
- **Rotation**: Horizontal, Vertical, Mixed (0° & 90°), Diagonal (±45°), Slight (±15°), Angled (±60°), or Any angle (360°)
- **Font Scaling**: Configurable min/max font sizes
- **Word Limit**: Control maximum number of words displayed
- **Phrase Splitting**: Break multi-word phrases into individual words
- **Word Filtering**: Exclude specific words, set minimum word length

### Interactivity
- Click to select words and cross-filter other visuals
- Ctrl/Cmd + Click for multi-select
- Right-click context menu for additional options
- Hover effects with scaling
- Rich tooltips with custom data
- Keyboard navigation (Tab, Enter, Space, Escape)

### Customization
- Background color (word colors auto-adjust for readability)
- Border styling (color, width, radius)
- Shadow effects
- Animation speed
- Padding and spacing

### Accessibility
- Full keyboard navigation support
- High contrast mode compatible
- ARIA labels for screen readers
- Automatic color contrast adjustment

### Localization
Supported languages:
- English (en-US)
- German (de-DE)
- Spanish (es-ES)
- French (fr-FR)
- Japanese (ja-JP)
- Portuguese - Brazil (pt-BR)
- Chinese - Simplified (zh-CN)

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

### Appearance
- Background color (word colors auto-adjust for readability)
- Corner radius
- Padding
- Border (show/hide, width, color)
- Shadow effect

### Words
- Minimum font size
- Maximum font size
- Font family
- Layout type (Archimedean, Rectangular, Compact, Centered, Random scatter)
- Rotation style
- Word spacing
- Maximum words
- Split phrases into words
- Word delimiters
- Minimum word length
- Exclude words (comma-separated list)

### Colors
- Color scheme selection
- Image data URI (for extracting colors from images)
- Colors to extract (2-12)
- Custom color palette (5 colors)

### Animation
- Enable/disable animations
- Animation duration (100-3000ms)
- Hover scale effect (100-150%)

## Version History

### 1.0.2.0
- Added localization support (7 languages)
- Added keyboard navigation and accessibility features
- Added context menu support
- Fixed linter errors (security improvements)
- Updated documentation
- New simplified icon design

### 1.0.1.0
- Added "From image" color extraction with base64 data URIs
- Added phrase splitting feature
- Added word exclusion and filtering options
- Added Report Theme color scheme
- Added more layout options (Compact, Centered, Random scatter)
- Added more rotation options
- Improved high contrast mode support
- Sentence case labels with descriptive tooltips

### 1.0.0.0
- Initial release
- Fluent 2 design implementation
- Multiple color schemes
- Animation support
- High contrast mode
