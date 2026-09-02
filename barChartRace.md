# Bar Chart Race Visual for Power BI

An animated ranked bar chart for Microsoft Power BI that shows how categories rise and fall over time — the racing bars format popularized on YouTube, built as a fully themable, keyboard-accessible custom visual.

![Bar Chart Race Visual](Bar%20chart%20race.png)

## What is Bar Chart Race?

Bar Chart Race animates a ranked list of categories across periods (months, years, quarters, or any numeric sort key). Bars grow and reorder as the animation plays, with a running leader subtitle, rank change indicators, an optional cumulative mode, and a scrubbable timeline.

Key features:

- **Smooth ranking animation** with configurable duration, easing, ping-pong and reverse playback
- **Cumulative or per-period mode** with an on-visual "Σ Cumulative" indicator in the leader subtitle
- **Rank change badges** (▲ up, ▼ down, ● unchanged, ★ new) with independent colors
- **Themable colors** pulled from the report theme by default — data colors, sentiment (positive/negative/neutral), foreground, background
- **Native font controls** (family + size + B/I/U) for every text element
- **Data label options** — auto/full/percent/field-format, plus an optional "% of leader" combo suffix
- **Scrubbable timeline** with play/pause, hover-pause, and a themed handle
- **Cross-visual selection** — click a bar to filter other visuals; Ctrl+click to multi-select
- **Keyboard navigation** — Tab, Arrow keys, Enter, Escape
- **High contrast mode** — OS palette with stroked bars for accessibility
- **Custom tooltips** for extra measure fields

## Key Benefits

### 🏁 Storytelling with rank movement

Bar chart races are one of the most engaging ways to show change over time — competitors overtaking each other, categories collapsing, new entrants breaking in. Perfect for executive readouts, sales rollups, sports/leaderboard content, and social-first data storytelling.

### 🎨 Theme-driven by default

Every color — bars, gradient endpoint, "#1" highlight, track, rank up/down/unchanged/new, headline text, labels, data label — inherits from your report theme (data colors 1–3, sentiment colors, foreground, background). Drop it into any themed report and it just fits. Override any color individually when you want to.

### 🅰️ Full native font controls

Title, leader subtitle, rank number, category label, group label, and data label each use Power BI's native FontControl — pick a font family, size, and toggle bold/italic/underline directly in the format pane (matching how core visuals work).

### 📊 Cumulative mode

Toggle **Cumulative** to sum values over time and race for the biggest running total (great for revenue-to-date, cumulative sales, YTD totals). The visual adds a small "Σ Cumulative" tag to the leader subtitle so viewers know they're watching a running total.

### ⌨️ Accessibility

- Full keyboard navigation (Tab, Arrow keys, Enter, Esc)
- High contrast mode with OS foreground/background/hyperlink and stroked bars
- ARIA labels announce rank, category, group, and value
- Screen-reader friendly
- Multi-visual selection API supported

### 🔗 Cross-filter and drill

- Click a bar to cross-filter other visuals
- Ctrl/Shift+click to multi-select
- Right-click for Power BI's native context menu (drill, include/exclude, export)
- Click empty space or press Esc to clear

## Data Fields

| Field | Required | Description |
|-------|----------|-------------|
| **Category** | ✅ Yes | The racer label (e.g. Product, Country, Team). One line per bar. |
| **Group** | Optional | Subtitle grouping under the category (e.g. Region under Product). Rendered as a smaller line under the category label. |
| **Period** | ✅ Yes | Numeric sort key for the animation (e.g. Month Number, Year). Determines animation order. |
| **Period Label** | Optional | Display label for the current period (e.g. Month Name). Falls back to the Period value if omitted. |
| **Value** | ✅ Yes | The measure that drives bar length (e.g. Sum of Sales). |
| **Tooltips** | Optional | Additional measures/columns to show in the hover tooltip. |

## How to Use

### Step 1: Add the Visual to Your Report

1. In Power BI Desktop, open the **Visualizations** pane
2. Click the **...** (more options) button
3. Select **Import a visual from a file**
4. Browse to the `.pbiviz` file and click **Open**
5. The Bar Chart Race icon appears in your visualizations pane

### Step 2: Prepare Your Data

Your data should be in a table shape with at minimum:

- A **category** column (product/country/team)
- A **period** column with a numeric sort value (month number, year, etc.)
- A **numeric measure** for the value

Optional but recommended:

- A **period label** column with human-readable text for the current period
- A **group** column for a subtitle under each bar
- Extra measures for the tooltip

### Step 3: Bind Fields

1. Click the Bar Chart Race visual to select it
2. Drag your fields to the appropriate data wells:
   - **Category**: e.g. Product Name
   - **Group** (optional): e.g. Region
   - **Period**: e.g. Month Number (used for sort)
   - **Period Label** (optional): e.g. Month Name
   - **Value**: e.g. Sum of Sales
   - **Tooltips** (optional): any extra measures

### Step 4: Press Play

The visual starts with a play button in the header. Click it to start the animation. Use the timeline at the bottom to scrub. Hover a bar to pause (if hover-pause is enabled).

### Step 5: Customize

Open the **Format** pane and customize the cards described below. All colors default to your report theme — override only what you want to change.

## Example: Sales Race by Product

### Sample Data

| Product | Region | Month | Month Name | Sales |
|---------|--------|-------|------------|-------|
| Alpha | North | 1 | Jan | 12000 |
| Alpha | North | 2 | Feb | 15000 |
| Bravo | South | 1 | Jan | 9000 |
| Bravo | South | 2 | Feb | 18000 |
| Charlie | East | 1 | Jan | 14000 |
| Charlie | East | 2 | Feb | 11000 |

### Step-by-Step: Basic Race

1. **Add the Bar Chart Race visual** to your canvas
2. **Configure fields:**
   - Category → `Product`
   - Group → `Region`
   - Period → `Month`
   - Period Label → `Month Name`
   - Value → `Sales`
3. **Press play** in the header
4. **Observe:** bars grow and reorder each period, with rank change badges (▲▼) next to each rank number

### Step-by-Step: Cumulative Year-to-Date Race

1. Start with the basic race above
2. In the format pane, expand **Rank** → **Top N**
3. Turn on **Cumulative**
4. Keep **Show cumulative indicator** on (default) — the leader subtitle will show `Σ Cumulative`
5. Optionally edit **Indicator text** (default "Cumulative")
6. **Observe:** each period now shows the running total, so the race is for biggest year-to-date value

### Step-by-Step: Percent-of-Leader Labels

1. Expand **Data label** → **Format**
2. Turn on **Also show % of leader**
3. Set **% decimals** to 1
4. Optionally change **% template** — `{p}` is replaced by the percent. Default: `" ({p}%)"`. Try `" — {p}%"` for a dash separator, or `" [{p} pct]"` for brackets
5. **Observe:** each bar's data label now shows the raw value plus the % relative to the leader, e.g. `$18,000 (100.0%)` for #1 and `$11,000 (61.1%)` for a smaller bar

## Formatting Options Reference

The visual has 7 cards in the Format pane, in this order: **Playback**, **Canvas & interaction**, **Header**, **Rank**, **Bars**, **Labels**, **Data label**. Every color has a theme default (shown as *Theme …*); if you leave it alone it inherits from the report theme, and if you set it explicitly your value wins.

### Playback

| Setting | Description | Default |
|---------|-------------|---------|
| Auto play | Start the animation automatically when the visual loads | On |
| Start delay (ms) | Delay before auto-play begins (0-10000) | 0 |
| Loop | Restart when the last period is reached | On |
| Direction | Forward / Reverse / Ping-pong | Forward |
| Speed | Slow (60s) / Normal (30s) / Fast (10s) / Custom | Custom |
| Custom duration (ms) | Total run time when Speed = Custom (1000-300000) | 30000 |
| Ease | Linear / Ease out / Ease in/out / Elastic | Ease out |

### Canvas & interaction

| Setting | Description | Default |
|---------|-------------|---------|
| Background | Canvas background color | *Theme background* |
| Show timeline | Display the timeline strip below the bars | On |
| Show play button | Display the play/pause button in the header | On |
| Enable timeline drag | Allow scrubbing the timeline handle with the mouse | On |
| Pause on hover | Pause the race while hovering a bar | Off |
| Reduce motion | Disable transitions for accessibility | Off |

### Header

Composite card with two groups: **Title** and **Leader subtitle**.

**Title group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show title | Show the header band with the period label | On |
| Font | Font family, size, bold, italic, underline | Segoe UI, 32, **B** |
| Color | Title text color | *Theme foreground* |
| Alignment | Left / Center / Right | Left |

**Leader subtitle group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show leader subtitle | Display the leader subtitle under the title | On |
| Prefix | Text before the leader name | `Leader: ` |
| Show group | Include the group name in the subtitle | On |
| Group separator | Text between category and group | ` · ` |
| Show value | Include the leader's value in the subtitle | On |
| Value separator | Text between name and value | ` — ` |
| Auto size to header | Shrink font to fit inside the header height | On |
| Font | Font family, size, bold, italic, underline | Segoe UI, 14 |
| Color | Leader text color | *Theme foreground* |
| Opacity % | Text opacity (0-100) | 70 |
| Alignment | Match title / Left / Center / Right | Match title |

When Cumulative is enabled and Show cumulative indicator is on, the text `• Σ <Indicator text>` is appended here.

### Rank

Composite card with three groups: **Top N**, **Rank number**, **Rank change**.

**Top N group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Number to show | How many top rows to display (3-50) | 10 |
| Cumulative value | Sum values over time (running total) | On |
| Show cumulative indicator | Append `• Σ …` to the leader subtitle when cumulative is on | On |
| Indicator text | Text after the Σ symbol | `Cumulative` |

**Rank number group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show rank number | Display #1, #2, etc. | On |
| Number format | `1` / `#1` / `1.` | `1` |
| Font | Font family, size, bold, italic, underline | Segoe UI, 20, **B** |
| Color | Rank number text color | *Theme foreground (secondary)* |

**Rank change group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show rank change | Show ▲▼●★ badges next to each rank number | On |
| Up | Color for rank going up (▲) | *Theme positive* |
| Down | Color for rank going down (▼) | *Theme negative* |
| Unchanged | Color for rank not changing (●) | *Theme neutral* |
| New entry | Color for newcomers (★) | *Theme foreground (tertiary)* |

### Bars

Composite card with three groups: **Layout**, **Color**, **Track**.

**Layout group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Row gap (%) | Vertical gap between bars (0-80) | 40 |
| Corner radius (%) | Bar corner rounding as % of bar height (0-50) | 50 |
| Opacity (%) | Bar fill opacity (10-100) | 100 |

**Color group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Color mode | Single color / Gradient by rank | Single color |
| Bar color | Bar fill color (or gradient start) | *Theme data color 1* |
| Gradient end color | End color of the rank gradient | *Theme data color 2* |
| Highlight #1 | Give the leader bar a distinct color | Off |
| #1 color | Leader bar color when Highlight #1 is on | *Theme data color 3* |

**Track group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show track | Show the background track behind each bar | On |
| Track color | Track fill color | *Theme neutral background* |

### Labels

Composite card with three groups: **Category (top line)**, **Group (second line)**, **Layout**.

**Category (top line) group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Font | Font family, size, bold, italic, underline | Segoe UI, 18, **B** |
| Color | Category label color | *Theme foreground* |

**Group (second line) group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show group | Show the group subtitle line under the category | On |
| Font | Font family, size, bold, italic, underline | Segoe UI, 13 |
| Color | Group label color | *Theme foreground (secondary)* |

**Layout group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Truncate at (chars, 0 = off) | Max characters before ellipsis (0 disables truncation) | 0 |

### Data label

Composite card with two groups: **Format** and **Display**.

**Format group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Format | None (use field format) / Auto (K/M/B) / Full number / Percent of leader | Auto (K/M/B) |
| Decimals | Decimal places (0-6) | 1 |
| Prefix | Text before the value | (empty) |
| Suffix | Text after the value | (empty) |
| Also show % of leader | Append a percent-of-leader suffix to the number | Off |
| % decimals | Decimals for the percent (0-4) | 1 |
| % template | Text pattern for the percent; `{p}` is replaced by the number | ` ({p}%)` |

**Display group:**

| Setting | Description | Default |
|---------|-------------|---------|
| Show value | Show the data label to the right of each bar | On |
| Font | Font family, size, bold, italic, underline | Segoe UI, 14 |
| Color | Data label color | *Theme foreground* |

## Cross-Visual Selection and Interaction

- **Click** a bar to select that category and cross-filter every other visual on the page
- **Ctrl / Shift + click** to add or remove a category from a multi-selection
- **Click the same bar again** or **click empty space** to clear the selection
- **Right-click** on a bar for the Power BI context menu (drill, include, exclude, export)
- **Right-click** on empty space for the visual-level context menu
- **Esc** clears the current selection
- **Tab** focuses the first bar, **Arrow Up/Down** moves the focus, **Enter / Space** selects the focused bar

Selected bars stay at full opacity; unselected bars dim to 35%.

## High Contrast Mode

When Windows high contrast mode is active, the visual automatically switches to the OS palette:

- Background → OS background
- All text (title, leader, rank, labels, data labels) → OS foreground
- Bars → OS foreground fill with a 1px OS foreground stroke
- Leader bar → OS hyperlink color for emphasis

## Theme Integration

Every color property has a theme-driven default. When you drop the visual into a themed report, it inherits:

- **Data colors 1, 2, 3** → bar single color, gradient end, leader #1 highlight
- **Positive / Negative / Neutral (sentiment)** → rank up / down / unchanged badges
- **Foreground / Foreground secondary / Foreground tertiary** → title, leader, rank number, category label, group label, data label, "new" badge
- **Background / Neutral background** → canvas background, track color

Any color you set in the format pane overrides the theme default for that property.

A matching custom theme, `Bar Chart Race Dark.json`, ships alongside the visual. It reproduces the original purple/gold palette and also styles the filter pane and page wallpaper to match. Apply it via **View → Themes → Browse for themes** in Power BI Desktop.

## Tips and Best Practices

### Data prep

- Make sure every (category, period) combination has a value — missing periods cause bars to jump. Use a measure that returns 0 for empty periods if needed.
- The **Period** field must be numeric and sortable. Use a `Month Number` or `Year * 100 + Month` column, not the display label.
- Put the human-readable text (e.g. "Jan 2024") in **Period Label**.

### Visual design

- Keep **Top N** at 10 or less for readability on standard-sized tiles; increase to 15–20 only for very tall canvases
- **Cumulative mode** works best with steadily growing measures (revenue, count) rather than volatile ones (daily temperature)
- **Highlight #1** in a contrasting color makes the leader instantly readable
- Turn on the **track** when bars are short — it gives visual continuity as bars grow into the space

### Performance

- Datasets up to ~10,000 rows (category × period) animate smoothly
- Faster **Frame duration** (400–600 ms) makes the race feel intense; slower (1000–1500 ms) is easier to read
- Enable **Reduce motion** if animation is distracting or a user has motion sensitivity preferences

### Accessibility

- Test with high contrast mode
- Provide meaningful category names — screen readers announce them via ARIA labels
- Data labels + rank change badges give non-color cues for progression
- Reduce motion is available for users with vestibular sensitivities

## Version History

### Version 1.0.22.0

**Selection, interaction, and accessibility:**

- **Cross-visual selection** — click a bar to filter other visuals; Ctrl/Shift + click for multi-select
- **Context menu** — right-click for the Power BI native menu (drill, include, exclude, export)
- **Keyboard navigation** — Tab, Arrow Up/Down, Enter, Space, Escape; ARIA labels on every row
- **High contrast mode** — swaps to OS palette with stroked bars

### Version 1.0.21.0

- Cumulative indicator moved to the leader subtitle as `• Σ Cumulative` suffix (no longer overlaps play button)

### Version 1.0.19.0 – 1.0.20.0

- Data label **% of leader** combo with customizable template
- Cumulative indicator (initial placement iterations)

### Version 1.0.18.0

- Bold rank number by default
- Leader #1 highlight uses theme data color 3
- Custom theme JSON (`Bar Chart Race Dark.json`) with matching filter pane and page wallpaper

### Version 1.0.17.0

- Themed timeline handle (no more hardcoded purple)

### Version 1.0.16.0

- Every color pulls from the report theme by default (data colors, sentiment, foreground, background)

### Version 1.0.14.0 – 1.0.15.0

- Native FontControl (family + size + B/I/U) for title, leader subtitle, rank number, category label, group label, and data label

### Version 1.0.13.0

- Leader subtitle formatting (prefix, group/value separators, alignment, color, opacity, font)

### Version 1.0.12.0

- Unique format-pane group names to prevent Rank/Data-label collisions

### Version 1.0.0.0

- Initial release
- Animated ranked bars with rank change badges
- Top N filter, cumulative mode, per-period mode
- Timeline scrubbing, play/pause, hover-pause
- Header with title and leader subtitle
- Category + group labels, data labels with format modes
- Custom tooltips

## Support

For issues, feature requests, or questions:

- **Website**: <https://datazoepowerbi.com>
- **Email**: <zoe@datazoepowerbi.com>

## Acknowledgments

This visual and documentation were created with the assistance of GitHub Copilot.

## License

MIT License - See LICENSE file for details.
