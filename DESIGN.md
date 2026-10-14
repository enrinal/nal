---
name: enrinal.is-a.dev
description: A personal letter in one calm column. Cool near-white ground, soft ink, one deep green.
colors:
  ground: "#fbfcfb"
  ink: "#1d2220"
  ink-2: "#4e5753"
  ink-3: "#6c7571"
  rule: "#e2e6e3"
  tint: "#eef3f0"
  green: "#1f6f5c"
  green-deep: "#155244"
  on-green: "#ffffff"
  ground-dark: "#141816"
  ink-dark: "#e4e9e6"
  ink-2-dark: "#a9b3ae"
  ink-3-dark: "#8a948f"
  rule-dark: "#2a312e"
  tint-dark: "#1c2220"
  green-dark: "#6fcfb4"
  green-deep-dark: "#93ddc8"
  on-green-dark: "#0c1512"
typography:
  display:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "clamp(2rem, 1.5rem + 2vw, 2.6rem)"
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: "-0.025em"
  headline:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "1.45rem"
    fontWeight: 650
    lineHeight: 1.25
    letterSpacing: "-0.015em"
  title:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 600
    lineHeight: 1.45
  body:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 400
    lineHeight: 1.65
  lede:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "1.2rem"
    fontWeight: 400
    lineHeight: 1.65
  meta:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: "0.95rem"
    fontWeight: 400
    lineHeight: 1.65
rounded:
  xs: "2px"
  sm: "0.25rem"
  md: "0.5rem"
  full: "50%"
spacing:
  xs: "0.75rem"
  sm: "1.25rem"
  md: "2.25rem"
  lg: "3.5rem"
  column: "40rem"
components:
  button-primary:
    backgroundColor: "{colors.green}"
    textColor: "{colors.on-green}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "0.8rem 1.15rem"
  button-primary-hover:
    backgroundColor: "{colors.green-deep}"
    textColor: "{colors.on-green}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "0.8rem 1.15rem"
  button-ghost-hover:
    backgroundColor: "{colors.tint}"
    textColor: "{colors.ink}"
  code-block:
    backgroundColor: "{colors.tint}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "1rem 1.15rem"
---

# Design System: enrinal.is-a.dev

## Overview

**Creative North Star: "The Personal Letter"**

One left-aligned reading column (40rem) on a cool near-white ground, set entirely in Hanken Grotesk. The visitor meets a person first and the structure second. Sections are separated by hairline rules and generous space, never by boxes, cards, or pills. A single deep green carries every link and the one filled action per view; dark mode mirrors the same roles with a lifted mint green.

Hierarchy comes from size and weight steps only. Motion is limited to underline and color transitions on one soft ease-out (`cubic-bezier(.16, 1, .3, 1)`, 200-250ms). Resume page must print to a clean one-column A4 PDF, so every screen rule has a monochrome print fallback.

**Key Characteristics:**
- One column, one typeface, one accent.
- Hairline rules and whitespace instead of containers.
- Weight and size steps (400, 550, 600, 650, 700) in place of display faces.
- Light and dark are the same system with mirrored roles.
- Print is a first-class output: nav, footer, and buttons drop; accent becomes black.

## Colors

A cool-tinted paper and soft ink, with one forest green used only where the visitor can act.

### Primary
- **Forest Green** (`green`): links, the filled button, the "open to roles" dot, the current-nav underline, focus ring, text selection. Mint (`green-dark`) in dark mode.
- **Deep Forest** (`green-deep`): hover state for links and the primary button.

### Neutral
- **Cool Paper** (`ground`): page background. **Night Moss** (`ground-dark`) in dark mode.
- **Soft Ink** (`ink`): headings and primary text. **Muted Ink** (`ink-2`): secondary prose, nav, intro paragraphs after the first. **Quiet Ink** (`ink-3`): dates, meta, list dashes, footer.
- **Hairline** (`rule`): section dividers, list separators, ghost button border.
- **Mint Tint** (`tint`): ghost-button hover, inline code, code blocks.
- Dark counterparts carry the `-dark` suffix and are applied through `prefers-color-scheme`; they are not a separate palette.

### Named Rules
**The One Green Rule.** Green appears only on interactive or status elements (links, the primary button, the availability dot, focus, selection). Never as a section fill or decorative accent.
**The Mirror Rule.** Every light token has a dark twin under the same custom-property name; new surfaces use the property, never a literal.

## Typography

**Display Font:** Hanken Grotesk (variable 100-900, roman and italic, self-hosted woff2, `system-ui, sans-serif` fallback)
**Body Font:** Hanken Grotesk
**Label/Mono Font:** `ui-monospace, "SF Mono", Menlo, monospace`, inline code and pre only.

**Character:** Friendly, upright grotesk; tabular numerals on by default. Headings are tighter-tracked bold, body is open at 1.65 line height.

### Hierarchy
- **Display** (700, clamp 2rem to 2.6rem, 1.15, -0.025em): page h1 (greeting, resume name, blog title, post title).
- **Headline** (650, 1.45rem, 1.25, -0.015em): section h2.
- **Title** (600, 1.0625rem to 1.1rem): job and company headings, post list titles (1.2rem in blog index).
- **Body** (400, 1.0625rem, 1.65): default text; article prose is 1.125rem at 1.75.
- **Lede** (400, 1.2rem): intro paragraphs and page intros; first paragraph in `ink`, the rest in `ink-2`.
- **Meta** (400, 0.95rem, `ink-3`): dates and contact lines.

### Named Rules
**The Steps-Not-Faces Rule.** Emphasis is a size or weight step within Hanken Grotesk; never a second family or case styling.
**The Measure Rule.** Text lives in the 40rem column; contact paragraph caps at 34rem.

## Layout

A single centered wrapper (`40rem` plus 1.25rem side padding), content left-aligned. Header: name left, nav right, 2rem vertical padding. Sections stack with 3.5rem top margin, 2.25rem top padding, and a 1px `rule` border above. Experience rows use a 6.5rem date column plus a fluid column; blog and recent-writing lists are date/title rows. Below 34rem, grids collapse to one column and dates move above or below titles. Footer sits 5rem below content with a hairline rule. Resume uses tighter 2.5rem section rhythm and a `max-content` / fluid definition grid for skills.

## Elevation & Depth

Flat. No shadows anywhere; depth is a hairline rule or a tint fill (`tint`) on hover and code. Focus is a 2px green outline offset 3px.

## Shapes

Soft but restrained: 0.5rem on buttons, code blocks, and images; 0.25rem on inline code; 2px on the focus outline; a 50% circle for the availability dot only. Borders are 1px `rule`; the ghost button uses the same border.

## Components

### Buttons
- **Shape:** 0.5rem radius, 1px border, 600 weight, inline icon at 1.05em.
- **Primary:** filled green, white text (dark text on mint in dark mode), padding 0.8rem 1.15rem. One per action row.
- **Hover:** background and border shift to `green-deep` over 200ms.
- **Ghost:** transparent, `rule` border, `ink` text; hover adds `tint` fill and `ink-3` border. Used for "Save as PDF".

### Links
Green with a 1px underline at 40% opacity that goes solid on hover. Nav and footer links are `ink-2` with no underline; current nav page gets a 2px green underline offset .45em.

### Action row
Primary button followed by plain text links, wrapping with a 1.5rem column gap.

### Availability line
A 0.55rem green dot beside a 550-weight sentence. Status only.

### Dated list rows
Date in `ink-3`, title in 600, one-line description in `ink-2`, separated by hairlines. Used for jobs, posts, and the blog index.

## Do's and Don'ts

### Do:
- **Do** separate sections with a 1px `rule` and spacing, not containers.
- **Do** reference custom properties (`--fg`, `--accent`, `--rule`) so dark mode and print follow.
- **Do** keep one filled button per action row and use text links for the rest.
- **Do** give every new screen rule a print fallback if it can appear on the resume.

### Don't:
- **Don't** add cards, skill pills, photo hero, or box shadows; the build uses none.
- **Don't** introduce a second typeface or all-caps labels.
- **Don't** use green for decoration, backgrounds, or non-interactive text.
- **Don't** animate beyond color and underline transitions.
