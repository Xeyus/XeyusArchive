# Limbus Archive Theme - Design Specification v1.1

This document outlines the design principles and implementation details of the Limbus Archive Hugo theme.

## 1. Core Visual Identity: CRT Archive Terminal

### 1.1 Hard-Edged Brutalism

**Principle**: Complete elimination of rounded corners throughout the design.

- **CSS Rule**: `border-radius: 0 !important;` applied globally
- **Rationale**: Creates a stark, institutional aesthetic reminiscent of 1980s terminal interfaces
- **All boundaries**: Defined by solid 1px lines only

### 1.2 Dynamic Embossed Logic

**Interactive Elements** (clickable text):
- Links, navigation items, RSS feed button
- **Default state**: Raised embossed appearance
- **Visual effect**: Box shadows creating physical depth
  ```css
  box-shadow: 
    2px 2px 0 rgba(0, 0, 0, 0.1),
    inset -1px -1px 0 rgba(0, 0, 0, 0.05),
    inset 1px 1px 0 rgba(255, 255, 255, 0.3);
  ```

**Active/Pressed State**:
- Switches to debossed (inset) appearance
- **Visual effect**: Inverted shadows for pressed button feel
  ```css
  box-shadow: 
    inset 2px 2px 3px rgba(0, 0, 0, 0.15),
    inset -1px -1px 0 rgba(255, 255, 255, 0.2);
  transform: translateY(1px);
  ```

**Reading Text** (titles, body content):
- Completely flat, no shadows
- **Rationale**: Prevents visual interference with reading
- **Accessibility**: Ensures clarity for users with reading disabilities

## 2. Color Palette (Low-Contrast / Accessibility Optimized)

| Element | Code | Purpose |
|---------|------|---------|
| **Background** | `#DEDAC8` | Aged paper / gray plaster, reduces blue light strain |
| **Main Text** | `#2B2B2B` | Dark gray ink, maintains clarity without harsh pure black |
| **Border Lines** | `#A19C8C` | Defines boundaries for sidebar, article containers |
| **Accent Color** | `#802020` | Dark red for link hovers, RSS markers - color-blind friendly |
| **Scanline Overlay** | `repeating-linear-gradient` | Full-screen 2px interval horizontal texture |

### 2.1 Accessibility Considerations

- **Contrast ratio**: Exceeds WCAG AA standards (4.5:1 for normal text)
- **Color-blind safety**: Dark red accent provides sufficient differentiation for protanopia/deuteranopia
- **Reduced blue light**: Warm background tone reduces eye strain during extended reading
- **High contrast mode support**: Alternative palette triggered by `prefers-contrast: high`

## 3. Spatial Layout & Behavior

### 3.1 Three-Column Structure

```
┌─────────────┬──────────────────┬──────────────┐
│  Navigation │   Content Feed   │     TOC      │
│   Console   │    (Masonry)     │   (Sticky)   │
│             │                  │              │
│  [Blog]     │  ┌──────────┐   │  Contents:   │
│   ├ Home    │  │ Article  │   │   • H2       │
│   ├ Posts   │  │          │   │   • H3       │
│   ├ About   │  └──────────┘   │   • H4       │
│   └ Archive │  ────────────    │              │
│             │  ┌──────────┐   │              │
│  [RSS_FEED] │  │ Article  │   │              │
└─────────────┴──────────────────┴──────────────┘
```

#### Left Column: Navigation Console
- **Top**: Blog name (large, bold, flat text)
- **Middle**: Navigation menu (embossed interactive items)
- **Bottom**: `[RSS_FEED]` button (prominent, not hidden)
- **Behavior**: Sticky positioning, full viewport height

#### Center Column: Content Pipeline
- **Layout**: Waterfall/masonry style
- **Separation**: 1px horizontal lines between articles
- **Container**: Each article in bordered box with scanline overlay
- **Typography**: Serif body font for readability

#### Right Column: Table of Contents
- **Position**: Sticky (scrolls with page)
- **Styling**: Bordered container matching site aesthetic
- **Headings**: H2/H3 only (bold treatment, no decorations)
- **Active state**: Current section highlighted with accent color

### 3.2 Responsive Breakpoints

**Desktop (1200px+)**: Full three-column layout

**Tablet (768px - 1200px)**: Two-column layout
- Navigation + Content only
- TOC hidden

**Mobile (< 768px)**: Single column
- Navigation horizontal/collapsed
- Content stacked
- Borders adjust to full width

## 4. Accessibility & Reading Experience

### 4.1 Typography

**UI Font** (Navigation, Headers):
- Primary: JetBrains Mono
- Fallback: Roboto Mono, Courier New, monospace
- **Purpose**: Provides typewriter aesthetic while maintaining clarity

**Body Font** (Content):
- Primary: Source Serif Pro
- Fallback: Georgia, serif
- **Purpose**: Reduces reading fatigue, improves comprehension

### 4.2 Reading Optimization

| Property | Value | Rationale |
|----------|-------|-----------|
| Line height | `1.8` | Ample vertical spacing for eye tracking |
| Letter spacing | `0.02em` | Prevents character crowding |
| Font size | `16px` | Optimal base size for readability |
| Max content width | `~65ch` | Prevents excessively long lines |

### 4.3 No Rounded Corners Strategy

**Accessibility benefit**: 
- Shape-based differentiation instead of color-dependent zones
- Extremely friendly to users with color vision deficiency
- Physical boundaries clearly defined through lines alone

### 4.4 Keyboard Navigation

- All interactive elements fully keyboard accessible
- Visual focus indicators (2px accent-colored outline)
- Logical tab order following visual hierarchy
- Skip-to-content link for screen readers

### 4.5 Motion & Animation

- Minimal transitions (0.2s max)
- Respects `prefers-reduced-motion` user preference
- No auto-playing animations or videos

## 5. Technical Implementation Notes

### 5.1 Scanline Effect

```css
body::before {
  content: '';
  position: fixed;
  background: repeating-linear-gradient(
    to bottom,
    transparent 0px,
    transparent 1px,
    rgba(0, 0, 0, 0.03) 1px,
    rgba(0, 0, 0, 0.03) 2px
  );
  pointer-events: none;
  z-index: 9999;
}
```

### 5.2 Border-Radius Prevention

```css
* {
  border-radius: 0 !important;
}
```

### 5.3 Emboss/Deboss Transitions

```css
.interactive-element {
  transition: all 0.1s ease;
}
```

Fast transitions preserve tactile feedback feel.

## 6. Content Guidelines

### 6.1 Writing Style

- **Titles**: Clear, descriptive, flat presentation
- **Body**: Academic/technical tone suitable for serif typography
- **Meta information**: Uppercase, monospace for data-like appearance

### 6.2 Image Treatment

- All images bordered with 1px `--color-border`
- No automatic rounding or fancy effects
- Alt text required for accessibility

### 6.3 Code Blocks

- Monospace font (JetBrains Mono)
- Subtle background differentiation
- Bordered container matching site style
- Syntax highlighting with muted color scheme

## 7. Future Considerations

### Potential Enhancements
- Dark mode variant with inverted CRT phosphor colors
- Print stylesheet maintaining brutalist aesthetic
- Optional grid overlay for ultra-technical appearance
- Archive timeline visualization

### Maintaining Design Integrity

When adding features, ask:
1. Does it require rounded corners? (If yes, redesign it)
2. Does it interfere with reading clarity? (If yes, remove it)
3. Is it accessible to color-blind users? (Must be yes)
4. Does it feel like a physical terminal? (Should be yes)

---

**Design Philosophy**: 
"Form follows function, but function includes emotion. The Limbus Archive theme should feel like discovering a forgotten government database from 1987 — institutional, mysterious, but ultimately serving the timeless purpose of preserving knowledge."

**Version**: 1.1  
**Last Updated**: 2025-03-18  
**Status**: Production Ready
