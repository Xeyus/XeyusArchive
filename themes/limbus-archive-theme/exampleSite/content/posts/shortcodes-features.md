---
title: "Shortcodes and Advanced Features"
date: 2025-03-17T15:30:00Z
categories: ["Documentation"]
tags: ["hugo", "shortcodes", "features"]
draft: false
---

This post demonstrates the advanced features and custom shortcodes available in the Limbus Archive theme.

## Custom Shortcodes

The theme includes several custom shortcodes to enhance your content.

### Callout Boxes

You can use callout boxes to highlight important information:

{{< callout info >}}
This is an **info** callout. Use it for general information or tips.
{{< /callout >}}

{{< callout warning >}}
This is a **warning** callout. Use it to alert readers about potential issues.
{{< /callout >}}

{{< callout error >}}
This is an **error** callout. Use it for critical information or errors.
{{< /callout >}}

{{< callout success >}}
This is a **success** callout. Use it for positive confirmations or completions.
{{< /callout >}}

### Terminal Blocks

For command-line instructions, use the terminal shortcode:

{{< terminal >}}
$ hugo new posts/my-new-post.md
Content created: content/posts/my-new-post.md

$ hugo server -D
Web Server is available at http://localhost:1313/
{{< /terminal >}}

### Figure with Caption

Display images with proper captions:

{{< figure src="https://via.placeholder.com/800x400/DEDAC8/2B2B2B?text=Example+Image" alt="Example image" caption="This is an example figure with a caption using the custom shortcode" >}}

## Markdown Features

### Tables

The theme supports standard Markdown tables:

| Feature | Status | Priority |
|---------|--------|----------|
| Responsive Layout | ✓ Complete | High |
| Syntax Highlighting | ✓ Complete | High |
| Dark Mode | ⚠ Planned | Medium |
| Search | ⚠ Planned | Low |

### Task Lists

- [x] Create theme structure
- [x] Implement responsive design
- [x] Add accessibility features
- [ ] Add dark mode variant
- [ ] Create theme documentation site

### Footnotes

You can add footnotes to your content[^1]. They appear at the bottom of the article[^2].

[^1]: This is the first footnote.
[^2]: This is the second footnote with more details.

## Code Highlighting

The theme supports syntax highlighting for many languages:

### Python

```python
def fibonacci(n):
    """Generate Fibonacci sequence up to n terms."""
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Generate first 10 Fibonacci numbers
for num in fibonacci(10):
    print(num, end=' ')
```

### JavaScript

```javascript
class Archive {
  constructor(name) {
    this.name = name;
    this.entries = [];
  }
  
  addEntry(entry) {
    this.entries.push({
      timestamp: Date.now(),
      content: entry
    });
  }
  
  getLatest() {
    return this.entries[this.entries.length - 1];
  }
}

const limbus = new Archive('Limbus');
limbus.addEntry('First entry');
```

### CSS

```css
.terminal-block {
  background: #1a1a1a;
  color: #00ff00;
  font-family: var(--font-ui);
  border: 1px solid var(--color-border);
  padding: 1rem;
}
```

## Mathematical Expressions

If you enable MathJax or KaTeX, you can include mathematical expressions:

Inline math: $E = mc^2$

Block math:

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

## Embedded Content

### YouTube Videos

You can embed YouTube videos (if you enable the privacy settings):

```markdown
{{</* youtube VIDEO_ID */>}}
```

### GitHub Gists

Embed GitHub Gists:

```markdown
{{</* gist username gist-id */>}}
```

## Content Organization

### Categories and Tags

This post is categorized under "Documentation" and tagged with "hugo", "shortcodes", and "features". These help organize content and make it discoverable.

### Table of Contents

Notice the Table of Contents in the right sidebar (on desktop). It automatically generates from your H2 and H3 headings, making it easy to navigate long articles.

## Performance Considerations

The theme is optimized for performance:

- Minimal CSS with no external frameworks
- Google Fonts loaded with `font-display: swap`
- Optional JavaScript (only for TOC enhancement)
- Semantic HTML for fast parsing
- No tracking or analytics by default

## Accessibility Features

Every element has been designed with accessibility in mind:

- ARIA labels where appropriate
- Semantic HTML structure
- Keyboard navigation support
- Color-blind friendly palette
- High contrast text
- Skip-to-content link
- Screen reader optimized

## Next Steps

Explore the theme's features by:

1. Reading the full documentation in `USAGE.md`
2. Checking out the design specification in `DESIGN.md`
3. Customizing colors in `static/css/main.css`
4. Creating your own shortcodes
5. Adding your own content

Happy writing! 📝
