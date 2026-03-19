# Contributing to Limbus Archive

Thank you for considering contributing to the Limbus Archive theme! This document provides guidelines for contributing.

## How to Contribute

### Reporting Bugs

**Before creating a bug report**, please check existing issues to avoid duplicates.

When filing a bug report, include:

- Hugo version (`hugo version`)
- Browser and OS
- Detailed steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable

### Suggesting Enhancements

Enhancement suggestions are welcome! Please:

- Describe the feature clearly
- Explain why it would be useful
- Provide examples or mockups if possible
- Consider how it fits with the brutalist aesthetic

### Pull Requests

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes**
4. **Test thoroughly** on different screen sizes
5. **Commit with clear messages**: `git commit -m 'Add amazing feature'`
6. **Push to your fork**: `git push origin feature/amazing-feature`
7. **Open a Pull Request**

## Design Guidelines

When contributing code or design changes, please adhere to the theme's core principles:

### Non-Negotiable Rules

1. **Zero border-radius**: No rounded corners anywhere
2. **No external frameworks**: Pure CSS only
3. **Accessibility first**: WCAG AA minimum
4. **Semantic HTML**: Use proper tags
5. **Progressive enhancement**: Works without JavaScript

### Color Palette

Stick to the defined color scheme:
- Background: `#DEDAC8`
- Text: `#2B2B2B`
- Borders: `#A19C8C`
- Accent: `#802020`

### Typography

- UI elements: JetBrains Mono or similar monospace
- Body text: Source Serif Pro or similar serif
- Line height: 1.8
- Letter spacing: 0.02em

### Interactive Elements

- Default state: Embossed (raised)
- Hover state: Color change to accent
- Active state: Debossed (pressed)
- Reading text: Flat (no shadows)

## Code Style

### HTML
```html
<!-- Use semantic HTML5 -->
<article class="article-container">
  <h1 class="article-title">Title</h1>
  <div class="article-content">...</div>
</article>
```

### CSS
```css
/* Use CSS custom properties */
.element {
  color: var(--color-text);
  font-family: var(--font-ui);
}

/* Group related properties */
.button {
  /* Positioning */
  display: inline-block;
  
  /* Box model */
  padding: 0.5rem 0.75rem;
  border: 1px solid var(--color-border);
  
  /* Typography */
  font-family: var(--font-ui);
  
  /* Visual */
  box-shadow: 2px 2px 0 rgba(0, 0, 0, 0.1);
  
  /* Misc */
  transition: all 0.1s ease;
}
```

### File Organization

```
layouts/
├── _default/          # Default templates
├── partials/          # Reusable components
└── shortcodes/        # Custom shortcodes

static/
└── css/
    └── main.css       # All styles in one file

archetypes/            # Content templates
```

## Testing Checklist

Before submitting a PR, test:

- [ ] Desktop (1400px+)
- [ ] Tablet (768-1200px)
- [ ] Mobile (< 768px)
- [ ] Keyboard navigation works
- [ ] Screen reader compatibility (NVDA/JAWS)
- [ ] No border-radius anywhere (inspect with DevTools)
- [ ] All interactive elements have embossed effect
- [ ] Colors maintain WCAG AA contrast
- [ ] Works with JavaScript disabled
- [ ] No console errors

## Documentation

When adding features, update:

- README.md (if user-facing)
- USAGE.md (for usage instructions)
- DESIGN.md (for design rationale)
- CHANGELOG.md (note the change)
- Example site content (if applicable)

## Questions?

Open an issue with the "question" label or start a discussion in GitHub Discussions.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for helping improve Limbus Archive!** 🙏
