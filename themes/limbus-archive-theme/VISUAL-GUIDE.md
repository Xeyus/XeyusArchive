# Limbus Archive Theme - Visual Guide

This document provides visual descriptions of the theme's key design elements.

## Layout Preview

### Desktop View (1400px+)

```
┌─────────────────────────────────────────────────────────────────────┐
│ [Scanline Overlay - Subtle horizontal lines across entire viewport] │
│                                                                       │
│  ┌─────────────┬────────────────────────────┬─────────────────┐    │
│  │ NAV CONSOLE │      CONTENT PIPELINE      │   TABLE OF      │    │
│  │             │                            │   CONTENTS      │    │
│  │ ┏━━━━━━━━┓  │  ╔══════════════════════╗ │                 │    │
│  │ ┃ LIMBUS ┃  │  ║ 2025.03.18 / Tech    ║ │  [Contents]     │    │
│  │ ┃ ARCHIVE┃  │  ║                      ║ │   ○ Overview    │    │
│  │ ┗━━━━━━━━┛  │  ║ Article Title Here   ║ │   ○ Features    │    │
│  │             │  ║                      ║ │   ○ Installation│    │
│  │ ▣ Home      │  ║ Article summary text ║ │                 │    │
│  │ ▣ Posts     │  ║ continues here with  ║ │  [Sticky scroll]│    │
│  │ ▣ About     │  ║ proper line spacing  ║ │                 │    │
│  │ ▣ Archive   │  ║ and serif typography ║ │                 │    │
│  │             │  ║                      ║ │                 │    │
│  │             │  ║ Read More →          ║ │                 │    │
│  │             │  ╚══════════════════════╝ │                 │    │
│  │             │  ─────────────────────────│                 │    │
│  │             │  ╔══════════════════════╗ │                 │    │
│  │             │  ║ Next Article...      ║ │                 │    │
│  │             │  ╚══════════════════════╝ │                 │    │
│  │             │                            │                 │    │
│  │ [RSS_FEED]  │                            │                 │    │
│  │             │                            │                 │    │
│  └─────────────┴────────────────────────────┴─────────────────┘    │
│                                                                       │
│  ───────────────────────────────────────────────────────────────    │
│         © 2025 Limbus Archive. Built with Hugo.                      │
└─────────────────────────────────────────────────────────────────────┘
```

Legend:
- `▣` = Embossed button (raised appearance)
- `╔══╗` = Bordered article container
- `○` = TOC link item
- Scanlines visible across entire page

## Color Palette Visualization

### Background & Text
```
████████████  #DEDAC8 - Background (Aged paper)
  ████████    #2B2B2B - Main text (Dark gray)
  ░░░░░░░░    #A19C8C - Border lines (Light gray)
  ▓▓▓▓        #802020 - Accent (Dark red)
```

## Interactive States

### Navigation Button States

**Default (Raised)**
```
┌───────────┐
│ ▲         │  ← Light highlight on top/left
│   HOME    │
│        ▼  │  ← Dark shadow on bottom/right
└───────────┘
```

**Hover**
```
┌───────────┐
│ ▲         │  
│   HOME    │  ← Text color changes to #802020
│        ▼  │  ← Border becomes red
└───────────┘
```

**Active/Pressed (Debossed)**
```
┌───────────┐
│ ▼         │  ← Shadows inverted
│   HOME    │  ← Button appears "pushed in"
│        ▲  │  ← Visually 1px lower
└───────────┘
```

## Typography Examples

### Navigation & UI Text
```
Font: JetBrains Mono
Style: Monospace, uppercase
Example: "HOME" "POSTS" "[RSS_FEED]"
```

### Article Titles & Body
```
Font: Source Serif Pro
Style: Serif, sentence case
Example: "Building Accessible Web Interfaces"
```

### Article Metadata
```
Font: JetBrains Mono
Style: Monospace, uppercase, small
Example: "2025.03.18 / TECHNOLOGY / 5 MIN READ"
```

## Component Details

### Article Container

```
╔═══════════════════════════════════════════╗
║ 2025.03.18 / CATEGORY / 5 MIN READ       ║
║                                           ║
║ Article Title in Source Serif Pro         ║
║                                           ║
║ Body text begins here with comfortable    ║
║ line-height of 1.8 and letter-spacing    ║
║ of 0.02em. Paragraphs are clearly        ║
║ separated with margin-bottom.            ║
║                                           ║
║ ## Subheading (Bold, Larger)             ║
║                                           ║
║ More content continues...                 ║
║                                           ║
║ Read More →                               ║
╚═══════════════════════════════════════════╝
```

### Table of Contents (Sticky)

```
┌─────────────────┐
│ TABLE OF        │
│ CONTENTS        │
├─────────────────┤
│ • Overview      │
│ • Installation  │
│   ○ Setup       │  ← H3 indented
│   ○ Config      │  ← H3 indented
│ • Usage         │
│ ● Current       │  ← Active section (red)
│ • Conclusion    │
└─────────────────┘
```

### Code Block

```
┌────────────────────────────────────┐
│ ```python                          │
│ def hello_world():                 │
│     print("Welcome to Archive")    │
│     return True                    │
│ ```                                │
└────────────────────────────────────┘
Background: rgba(0,0,0,0.05)
Border: 1px solid #A19C8C
Font: JetBrains Mono
```

### Blockquote

```
│ This is a blockquote with a dark red
│ left border and italic text. It stands
│ out from the body while maintaining
│ readability.
```

### Pagination

```
┌──────┐  ┌──────────────┐  ┌──────┐
│ ← Prev│  │ Page 2 of 5  │  │Next →│
└──────┘  └──────────────┘  └──────┘
  (embossed)    (flat)      (embossed)
```

## Responsive Behavior

### Tablet (768px - 1200px)
```
┌─────────────┬────────────────────────┐
│ NAVIGATION  │   CONTENT PIPELINE     │
│             │                        │
│             │  (TOC removed)         │
└─────────────┴────────────────────────┘
```

### Mobile (< 768px)
```
┌────────────────────────────────────┐
│ LIMBUS ARCHIVE                     │
├────────────────────────────────────┤
│ ▣ Home ▣ Posts ▣ About ▣ Archive  │
├────────────────────────────────────┤
│                                    │
│  ╔══════════════════════════════╗ │
│  ║ Article 1                    ║ │
│  ╚══════════════════════════════╝ │
│                                    │
│  ╔══════════════════════════════╗ │
│  ║ Article 2                    ║ │
│  ╚══════════════════════════════╝ │
│                                    │
└────────────────────────────────────┘
```

## Accessibility Features

### Focus Indicators
```
┌───────────┐
│ ▣ HOME    │  ← Normal state
└───────────┘

┏━━━━━━━━━━━┓
┃ ▣ HOME    ┃  ← Focused (2px red outline)
┗━━━━━━━━━━━┛
```

### Screen Reader Experience

Navigation structure:
1. Skip to main content (hidden link)
2. Site title (H1)
3. Navigation menu (nav > ul)
4. Main content area
5. Table of Contents (nav > aside)
6. Footer

All interactive elements have proper ARIA labels and semantic HTML.

## Special Effects

### Scanline Texture
- 2px repeating horizontal lines
- Opacity: 0.03 (very subtle)
- Applied via `::before` pseudo-element
- Covers entire viewport
- Does not interfere with interactions

### Emboss Shadow System

**Raised (Default)**
```css
box-shadow: 
  2px 2px 0 rgba(0,0,0,0.1),           /* Outer shadow */
  inset -1px -1px 0 rgba(0,0,0,0.05),  /* Inner dark */
  inset 1px 1px 0 rgba(255,255,255,0.3); /* Inner light */
```

**Pressed (Active)**
```css
box-shadow: 
  inset 2px 2px 3px rgba(0,0,0,0.15),    /* Inner shadow */
  inset -1px -1px 0 rgba(255,255,255,0.2); /* Inner light */
transform: translateY(1px);               /* Physical push */
```

---

## Testing Checklist

When implementing or modifying the theme, verify:

- [ ] No `border-radius` anywhere (inspect with DevTools)
- [ ] Emboss effects work on all interactive elements
- [ ] Scanlines visible but not distracting
- [ ] Color contrast meets WCAG AA standards
- [ ] Keyboard navigation works completely
- [ ] TOC updates on scroll
- [ ] Responsive layouts at all breakpoints
- [ ] Fonts load correctly from Google Fonts
- [ ] Print styles maintain structure

---

**Note**: Actual visual appearance depends on browser rendering and font availability. These ASCII diagrams represent the intended structure and spacing.
