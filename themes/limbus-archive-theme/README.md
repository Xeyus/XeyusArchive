# Limbus Archive

A brutalist, CRT terminal-inspired Hugo theme with a strong focus on accessibility and readability.

![Version](https://img.shields.io/badge/version-1.1-darkred)
![Hugo](https://img.shields.io/badge/hugo-0.120%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## Design Philosophy

**Limbus Archive** embodies the aesthetic of a 1980s CRT terminal crossed with modern accessibility standards. Every design decision serves both form and function:

- **Hard-edged brutalism**: Zero border-radius throughout
- **Tactile UI**: Dynamic embossed/debossed effects on interactive elements
- **Low-contrast readability**: Optimized for reduced eye strain
- **Scanline texture**: Subtle CRT overlay for atmospheric authenticity
- **WCAG compliance**: Color-blind friendly, high readability, keyboard navigation

## Features

✅ Three-column layout (Navigation / Content / TOC)  
✅ Responsive design with mobile-first approach  
✅ Built-in Table of Contents with active section tracking  
✅ RSS feed support with prominent [RSS_FEED] button  
✅ Zero JavaScript required for core functionality  
✅ Accessibility: ARIA labels, keyboard navigation, screen reader optimized  
✅ Typography: Monospaced UI font + serif body font  
✅ Syntax highlighting support  
✅ Pagination for list pages  

## Installation

### As a Git Submodule

```bash
cd your-hugo-site
git submodule add https://github.com/yourusername/limbus-archive.git themes/limbus-archive
```

Then update your `config.toml`:

```toml
theme = "limbus-archive"
```

### Manual Installation

Download the theme and place it in your `themes/` directory:

```bash
cd your-hugo-site/themes
git clone https://github.com/yourusername/limbus-archive.git
```

## Configuration

### Basic Setup

```toml
baseURL = "https://yoursite.com/"
languageCode = "en-us"
title = "Your Archive Name"
theme = "limbus-archive"

[params]
  description = "Your site description"
  footer = "© 2025 Your Name"
  mainSections = ["posts", "blog"]

# Enable Table of Contents
[markup.tableOfContents]
  endLevel = 3
  startLevel = 2

# Navigation menu
[[menu.main]]
  name = "Home"
  url = "/"
  weight = 1

[[menu.main]]
  name = "Posts"
  url = "/posts/"
  weight = 2

[[menu.main]]
  name = "About"
  url = "/about/"
  weight = 3
```

### Color Customization

The theme uses CSS variables for easy customization. Edit `static/css/main.css`:

```css
:root {
  --color-background: #DEDAC8;  /* Background (aged paper) */
  --color-text: #2B2B2B;        /* Main text (dark gray) */
  --color-border: #A19C8C;      /* Border lines */
  --color-accent: #802020;      /* Links/highlights (dark red) */
}
```

### Typography

Default fonts:
- **UI/Headers**: JetBrains Mono (monospace)
- **Body text**: Source Serif Pro (serif)

To use different fonts, update the Google Fonts link in `layouts/_default/baseof.html` and modify the CSS variables:

```css
:root {
  --font-ui: 'Your Monospace Font', monospace;
  --font-body: 'Your Serif Font', serif;
}
```

## Content Creation

Create a new post:

```bash
hugo new posts/my-first-post.md
```

Example front matter:

```yaml
---
title: "My First Post"
date: 2025-03-18
categories: ["Technology"]
tags: ["Hugo", "Web Design"]
draft: false
---
```

## Design Details

### Visual Hierarchy

1. **Clickable elements** (links, buttons): Raised embossed effect
2. **Active/pressed state**: Depressed (inset) effect
3. **Reading text** (titles, body): Flat, no shadows

### Accessibility Features

- Color-blind safe palette (dark red accent)
- 1.8x line-height for easy reading
- Letter-spacing for reduced crowding
- Keyboard-only navigation support
- `prefers-contrast: high` media query support
- `prefers-reduced-motion` support
- Semantic HTML structure

### Responsive Breakpoints

- **Desktop**: 3-column layout (Nav / Content / TOC)
- **Tablet** (≤1200px): 2-column layout (Nav / Content)
- **Mobile** (≤768px): Single column, stacked layout

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Progressive enhancement approach
- Graceful degradation for older browsers

## Development

To work on the theme locally:

```bash
# Clone the repository
git clone https://github.com/yourusername/limbus-archive.git
cd limbus-archive/exampleSite

# Run Hugo server
hugo server --themesDir ../..
```

Visit `http://localhost:1313` to preview.

## Credits

Inspired by:
- Brutalist web design principles
- 1980s CRT terminal aesthetics
- Project Limbus (fictional archive concept)
- Accessibility-first design methodology

## License

MIT License - feel free to use and modify for your projects.

## Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request with clear description

---

**Built with ❤️ and pixels**  
For questions or feedback: [your-email@example.com]
