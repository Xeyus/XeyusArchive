---
title: "Welcome to Limbus Archive"
date: 2025-03-18T10:00:00Z
categories: ["Meta"]
tags: ["announcement", "theme", "design"]
draft: false
---

Welcome to the Limbus Archive theme demonstration. This is an example post showcasing the key features and design elements of this brutalist, CRT-inspired Hugo theme.

## Design Philosophy

The Limbus Archive theme embraces a **hard-edged brutalist aesthetic** inspired by 1980s CRT terminals and institutional databases. Every design decision serves both form and function:

- Complete elimination of rounded corners
- Dynamic embossed/debossed UI elements
- Low-contrast color scheme optimized for extended reading
- Scanline texture overlay for atmospheric authenticity

### Typography & Readability

This theme uses two carefully selected font families:

1. **JetBrains Mono** for UI elements, headers, and metadata
2. **Source Serif Pro** for body text and long-form reading

The combination provides a typewriter-like aesthetic while maintaining excellent readability. With a line-height of 1.8 and letter-spacing of 0.02em, the text has ample breathing room.

## Interactive Elements

Try clicking the navigation items in the left sidebar. Notice how they have a raised, embossed appearance that switches to a debossed (pressed) state when clicked. This tactile feedback creates a physical computing experience.

### Code Examples

The theme includes beautiful syntax highlighting:

```python
def greet_archive():
    """Welcome message for new visitors."""
    print("Welcome to the Limbus Archive")
    print("Where brutalism meets accessibility")
    return True

if __name__ == "__main__":
    greet_archive()
```

Code blocks use the monospace font with a subtle background to differentiate them from regular text.

## Accessibility Features

This theme takes accessibility seriously:

- **Color-blind friendly**: The dark red accent color provides clear differentiation
- **Keyboard navigation**: All interactive elements are fully accessible via keyboard
- **Screen reader optimized**: Semantic HTML and ARIA labels throughout
- **Reduced motion support**: Respects user's motion preferences
- **High contrast mode**: Alternative palette for users who need it

> "The best design is invisible to those who don't need it, and essential to those who do."

## Content Organization

### Three-Column Layout

The desktop layout uses a three-column structure:

1. **Left**: Navigation console with site menu and RSS feed
2. **Center**: Main content pipeline (you're reading this now)
3. **Right**: Table of Contents for easy navigation

On smaller screens, this collapses gracefully to maintain readability.

### Responsive Design

The theme adapts to different screen sizes:

- **Desktop (1200px+)**: Full three-column layout
- **Tablet (768-1200px)**: Two columns (nav + content)
- **Mobile (< 768px)**: Single column, stacked layout

## Visual Elements

### Images

Images are displayed with a subtle border matching the theme's aesthetic:

![Example placeholder](https://via.placeholder.com/800x400/DEDAC8/2B2B2B?text=Limbus+Archive+Theme)

### Lists

Ordered and unordered lists work as expected:

1. First item in ordered list
2. Second item with more details
3. Third item concluding the sequence

Unordered lists use standard bullets:

- Terminal aesthetics
- Brutalist design
- Accessibility focus
- CRT-inspired visuals

### Blockquotes

Quotes are highlighted with a dark red border on the left:

> The Limbus Archive theme represents a fusion of institutional brutalism and modern web accessibility standards. It proves that stark, minimal design can coexist with user-friendly, inclusive experiences.

## Technical Implementation

The theme is built with:

- Pure HTML5 and CSS3
- Zero JavaScript required for core functionality
- Semantic markup for SEO and accessibility
- CSS Grid for layout
- CSS custom properties for easy theming

### Scanline Effect

The subtle scanline texture you see across the page is created using a CSS gradient overlay. It adds atmosphere without interfering with readability:

```css
body::before {
  background: repeating-linear-gradient(
    to bottom,
    transparent 0px,
    transparent 1px,
    rgba(0, 0, 0, 0.03) 1px,
    rgba(0, 0, 0, 0.03) 2px
  );
}
```

## Getting Started

To use this theme for your own Hugo site:

```bash
# Add as submodule
git submodule add https://github.com/yourusername/limbus-archive.git themes/limbus-archive

# Configure in config.toml
theme = "limbus-archive"
```

Check the `README.md` and `USAGE.md` files for detailed installation and customization instructions.

## Customization

The theme uses CSS custom properties, making it easy to customize colors:

```css
:root {
  --color-background: #DEDAC8;
  --color-text: #2B2B2B;
  --color-border: #A19C8C;
  --color-accent: #802020;
}
```

Simply override these values in your own CSS to create your unique variation.

## Conclusion

The Limbus Archive theme offers a unique aesthetic for writers, developers, and digital archivists who appreciate brutalist design combined with modern web standards. It's perfect for:

- Personal blogs with a technical focus
- Developer portfolios
- Documentation sites
- Digital archives and collections
- Anyone who loves CRT aesthetics

Thank you for exploring this theme. If you have questions or feedback, please check the repository's Issues page or Discussions section.

---

**Happy archiving!** 📁
