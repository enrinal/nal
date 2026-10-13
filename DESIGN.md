---
name: enrinal.is-a.dev
description: A backend engineer's career set as a railway timetable. White paper, black ink, one signal red.
colors:
  paper: "#ffffff"
  ink: "#121212"
  ink-2: "#4b4b48"
  ink-3: "#6b6b67"
  rule: "#dcdcd8"
  band: "#f3f3f1"
  signal: "#d8231f"
  signal-ink: "#b51b17"
  ink-on-close: "#c9c9c5"
typography:
  display:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "clamp(2.6rem, 1.2rem + 5.4vw, 5.75rem)"
    fontWeight: 800
    lineHeight: 0.95
    letterSpacing: "-0.03em"
  headline:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "clamp(1.5rem, 1.1rem + 1.4vw, 2.1rem)"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.015em"
  title:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "clamp(1.35rem, 1.1rem + 0.8vw, 1.75rem)"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.015em"
  body:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 400
    lineHeight: 1.6
  label:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "0.72rem"
    fontWeight: 700
    lineHeight: 1.6
    letterSpacing: "0.08em"
rounded:
  none: "0"
  dot: "50%"
spacing:
  gutter: "clamp(1rem, 4vw, 2.5rem)"
  measure: "68ch"
  wide: "72rem"
  column: "8.5rem"
  gap: "2rem"
components:
  button:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.ink}"
    rounded: "{rounded.none}"
    padding: "0.85rem 1.15rem"
  button-hover:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
  button-primary:
    backgroundColor: "{colors.signal}"
    textColor: "{colors.paper}"
    rounded: "{rounded.none}"
    padding: "0.85rem 1.15rem"
  button-primary-hover:
    backgroundColor: "{colors.signal-ink}"
    textColor: "{colors.paper}"
  nav-link-current:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
    padding: "0.35rem 0.7rem"
  close-band:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
    padding: "clamp(2rem, 5vw, 3.5rem)"
---

# Design System: enrinal.is-a.dev

## Overview

**Creative North Star: "The Timetable"**

The site is a Kursbuch page: white paper, black ink, ruled rows, and a vertical route line with a station dot per company. Dates are departures, set in tabular figures. The current role is the train on the platform. Density is calm and editorial, with generous vertical gaps between ruled sections and a fixed 8.5rem left column that holds dates.

One neo-grotesk (Archivo, variable weight and width) does all the work. Hierarchy comes from weight and width: condensed heavy for headings, normal width for reading. Depth comes from rules and ink, not shadow. Red appears only for "now" and the primary action.

**Key Characteristics:**
- Ruled structure: 3px ink rules open sections, 1px grey rules separate rows.
- Left date column (8.5rem) aligned across board, route, post list, and resume.
- Square corners everywhere except the station dots.
- Tabular figures set on body, so every date and number aligns.
- Print parity: the resume page drops chrome and becomes the PDF.

## Colors

A near-monochrome paper-and-ink palette with a single signal red.

### Primary
- **Signal Red** (`signal`): the "now" dot, the "Open to roles" dot, the primary button fill, the focus ring, and text selection.
- **Signal Ink** (`signal-ink`): the darker red for red text (status label), primary-button hover, link hover, and links inside prose; it holds contrast on white.

### Neutral
- **Paper White** (`paper`): page ground and button ground.
- **Ink Black** (`ink`): body text, heavy rules, current nav item, the closing band.
- **Graphite** (`ink-2`): secondary text, roles, descriptions.
- **Pencil** (`ink-3`): small uppercase labels and scrollbar.
- **Rule Grey** (`rule`): 1px row dividers.
- **Band Grey** (`band`): row hover and code backgrounds.
- **Soft Ink Text** (`ink-on-close`): body text on the black closing band.

### Named Rules
**The One Signal Rule.** Red marks "now" or the one action to take, and nothing else. It is never decoration, never a section color.

## Typography

**Display / Body / Label Font:** Archivo (variable, woff2, 100-900 weight, 62-125% width) with system-ui sans-serif fallback.

**Character:** A workhorse grotesk used like station signage: heavy and condensed up top, plain and wide for reading. No serif, no mono display (mono only for inline code, `ui-monospace`).

### Hierarchy
- **Display** (800, 2.6-5.75rem fluid, 0.95, width 78%): the name on the home board; blog index title uses the same width at up to 4.25rem.
- **Headline** (800, 1.5-2.1rem, 1.1, width 85%): section titles ("Route so far", "Notable work", "Stack").
- **Title** (800, 1.35-1.75rem, 1.1, width 85%): company names on the route; the closing band heading is a larger 800/80% variant.
- **Body** (400, 1.0625rem, 1.6): everything else; prose steps up to 1.125rem/1.7 at a 68ch measure.
- **Label** (700, 0.72rem, +0.08em, uppercase, width 85%): table column heads and the resume's left-column section names.

### Named Rules
**The Width Ladder Rule.** Hierarchy is weight plus `font-stretch`: 78-85% for display and headings, 90-95% for sub-lines and buttons, 100% for reading text.
**The Tabular Rule.** `font-variant-numeric: tabular-nums` stays on at the body level so dates and metrics line up.

## Layout

A single 72rem centered column with a fluid gutter (`clamp(1rem, 4vw, 2.5rem)`). Home uses an 8.5rem date column plus fluid content: the board row is a four-cell grid (date, name, place, status), the route puts dates, dot, and body on one grid with the line at the dot center. Section gaps run roughly 4.5-8rem via `clamp`. Resume uses a 9rem label column with a 52rem max, and a 22mm column in print on A4.

Breakpoints: 64rem collapses the board to three columns; 44rem stacks everything, moves the route line to the left edge with dates above each stop, turns the timetable table into stacked rows, and makes the skills and closing band single column.

## Elevation & Depth

Flat. No shadows anywhere. Depth comes from ink rules (3px heavy, 1px light), a Band Grey hover fill on rows, and one full-bleed-within-column black closing band.

### Named Rules
**The Flat Paper Rule.** Surfaces never lift. State change is a fill swap (white to ink, red to deep red) or a rule, never a shadow.

## Shapes

Hard right angles: buttons, nav items, the closing band, code blocks, and table cells have zero radius. The only curve is the circle: 1rem station dots (3px ink ring, red-filled when current) and the 0.6rem status dot. Borders are 2px on buttons, 3px on heavy rules, 1px on dividers. The header mark is a 0.85rem red square.

## Components

### Buttons
- **Shape:** square, 2px ink border, padding 0.85rem 1.15rem, bold 1rem at width 90%.
- **Default:** paper fill, ink text; hover inverts to ink fill, paper text (0.2s, ease-out expo).
- **Primary:** signal fill and border, white text; hover to Signal Ink. Carries a square-cap 2px stroke inline SVG icon where one exists.
- **On the dark band:** ink fill with paper border; hover inverts to paper; primary hover goes white with ink text.

### Navigation
Header: the red-square mark plus "enrinal" wordmark at left (800, width 85%), three text links at right (600, 0.95rem, graphite). Hover reveals a 1px rule border; the current page is a solid ink block with white text. A 3px ink rule runs full width beneath. The footer mirrors it: 1px ink rule, name and place at left, plain text links at right.

### Departure Board Entry
The home first-view row: tabular years at left, name at display scale with role line, place and zone, red "Open to roles" status with dot. Actions sit below a 1px rule, with the primary action first and "Full resume" pushed right.

### Route
Ordered list with a 3px ink vertical line between stops, ringed dots, and years right-aligned in the date column. The current stop's dot is red and pulses once; the line draws downward on scroll where scroll-driven animation is supported. Both are static under reduced motion.

### Timetable Table
Three columns (Problem, Approach, Result) under a 3px ink head rule, 1px row rules, Band Grey row hover; stacks to blocks below 44rem.

### Closing Band
Black block with a large heading, one sentence, a primary action, and a secondary action.

## Do's and Don'ts

### Do:
- **Do** use red only for the current role or position, status, and the single primary action.
- **Do** keep dates in the left column in tabular figures.
- **Do** separate sections with 3px ink rules and rows with 1px Rule Grey.
- **Do** keep corners square and reserve circles for station dots.
- **Do** keep focus visible: 2px signal outline with 3px offset.
- **Do** keep the resume print-clean: hide header, footer, and `.no-print` controls; use mm and pt units.

### Don't:
- **Don't** add shadows, gradients, or blur.
- **Don't** add a second accent color or color the sections.
- **Don't** introduce a serif or a mono display face.
- **Don't** add avatars, skill pills, or logo walls; proof is resume facts only.
- **Don't** use red for body-size link text on white; use Signal Ink.
