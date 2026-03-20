---
name: hierarchical-tagging
description: Hierarchical tag system based on library classification principles for
  content classification. Use when the user asks to tag, categorize, or label content
  (files, bookmarks, notes, articles, books, documents, etc.) or when they want to
  organize information using tags. Also use when user asks to suggest tags, review
  existing tags, or improve tag organization.
type:
- note
tags: ["life/pkm", "formal-science/logic"]
状态: null
date: '2026-01-28T23:53:00+08:00'
title: 打tag标准
series: []
---
[[QUICK_REFERENCE]]

[[标签分配方案]]

以及配套的 [[type-standards]]

具体列表位于 [[Pre-defined Tags]]

---

## name: hierarchical-tagging description: Hierarchical tag system based on library classification principles for content classification. Use when the user asks to tag, categorize, or label content (files, bookmarks, notes, articles, books, documents, etc.) or when they want to organize information using tags. Also use when user asks to suggest tags, review existing tags, or improve tag organization.

# Hierarchical Tagging System (Library Classification Based)

A structured knowledge domain classification system following library science principles with two-level hierarchy, based on established library classification standards.

## Classification Principles

Based on library classification standards:

1. **Single Criterion**: Each level uses ONE classification standard
    - Level 1: By knowledge/practice domain (what the content is about)
    - Level 2: By subdomain within that field
2. **Exhaustive Coverage**: Child categories fully cover parent category
    - No gaps in coverage
    - No content falls outside the system
3. **Mutual Exclusivity**: Categories at same level don't overlap
    - Each item belongs to ONE primary domain
    - No sibling categories are compatible concepts

## Tag Structure

Format: `domain/subdomain`

- **Level 1**: Broad knowledge domain (follows established library classification)
- **Level 2**: Specific subdomain (stops at second level)
- **Uncertainty**: Use top-level only when subdomain unclear

## Level 1: Knowledge Domains

Based on standard library classification with user-specific additions:

```
philosophy/              # Philosophy - fundamental questions
religion/                # Religion - religious studies, theology
occultism/              # Occultism - esoteric, mystical traditions
psychology/             # Psychology - human mind and behavior
psychoanalysis/         # Psychoanalysis - psychoanalytic theory and practice
social-science/         # Social Sciences - human society
natural-science/        # Natural Sciences - natural phenomena
formal-science/         # Formal Sciences - abstract structures
medical-science/        # Medicine - human health
engineering/            # Engineering - technical implementation
applied-arts/           # Applied Arts - functional artistic creation
fine-arts/             # Fine Arts - aesthetic artistic creation
linguistics/            # Linguistics - study of language itself
literature/             # Literature - literary creation and study
life-practice/          # Life Practice - daily life skills
history/                # History - study of past events
```

## Critical Definition: literature/

**literature/ = Literary creation AND literary studies**

✅ Included:

- Fictional works: novels, short stories, poetry, drama
- Literary criticism and theory
- Literary movements and styles
- Textual analysis

❌ NOT included (classify by content domain):

- Political essays → `social-science/politics`
- Philosophical essays → `philosophy/[subdomain]`
- Travel writing → `life-practice/travel`
- Biographies → relevant domain or `history/`
- Product reviews → `life-practice/consumption`
- News articles → `social-science/communication`

**Core principle**: Classify by CONTENT, not by WRITING STYLE

## Level 2: Subdomain Examples

### philosophy/

```
philosophy/metaphysics          # Metaphysics, ontology
philosophy/epistemology         # Theory of knowledge
philosophy/ethics              # Moral philosophy
philosophy/logic               # Philosophical logic
philosophy/aesthetics          # Philosophy of beauty and art
philosophy/political           # Political philosophy
philosophy/mind                # Philosophy of mind
philosophy/language            # Philosophy of language
philosophy/eastern             # Eastern philosophy traditions
philosophy/western             # Western philosophy traditions
```

### religion/

```
religion/christianity          # Christianity
religion/islam                 # Islam
religion/buddhism             # Buddhism
religion/hinduism             # Hinduism
religion/judaism              # Judaism
religion/comparative          # Comparative religion
religion/theology             # Theology
religion/history              # Religious history
```

### occultism/

```
occultism/mysticism           # Mysticism
occultism/esotericism         # Esoteric traditions
occultism/magic               # Magical practices
occultism/alchemy             # Alchemy
occultism/divination          # Divination, tarot, astrology
occultism/hermetic            # Hermetic tradition
```

### psychology/

```
psychology/cognitive          # Cognitive psychology
psychology/developmental      # Developmental psychology
psychology/social            # Social psychology
psychology/clinical          # Clinical psychology
psychology/behavioral        # Behavioral psychology
psychology/experimental      # Experimental psychology
```

### psychoanalysis/

```
psychoanalysis/freudian       # Freudian psychoanalysis
psychoanalysis/jungian        # Jungian analytical psychology
psychoanalysis/lacanian       # Lacanian psychoanalysis
psychoanalysis/object-relations # Object relations theory
psychoanalysis/contemporary   # Contemporary psychoanalytic theory
```

### social-science/

```
social-science/politics             # Political science, commentary, analysis
social-science/economics            # Economics, economic commentary
social-science/sociology            # Sociology
social-science/anthropology         # Anthropology
social-science/law                 # Law, legal analysis
social-science/education           # Education studies
social-science/communication       # Communication, media, journalism
social-science/geography           # Human geography
```

**Key**: Political commentary, economic analysis, social critiques belong here regardless of writing style.

### natural-science/

```
natural-science/physics            # Physics
natural-science/chemistry          # Chemistry
natural-science/biology           # Biology
natural-science/earth-science     # Earth sciences, geology
natural-science/astronomy         # Astronomy, cosmology
natural-science/ecology           # Ecology, environmental science
```

### formal-science/

```
formal-science/mathematics        # Mathematics
formal-science/logic             # Formal logic, symbolic logic
formal-science/statistics        # Statistics
formal-science/computer-science  # Theoretical computer science
```

### medical-science/

```
medical-science/clinical        # Clinical medicine
medical-science/surgery         # Surgery
medical-science/pharmacology    # Pharmacology
medical-science/public-health   # Public health, epidemiology
medical-science/psychiatry      # Psychiatry (medical approach)
```

### engineering/

```
engineering/software             # Software engineering
engineering/electrical           # Electrical engineering
engineering/mechanical           # Mechanical engineering
engineering/civil               # Civil engineering
engineering/chemical            # Chemical engineering
engineering/information         # Information technology (applied CS)
```

### applied-arts/

```
applied-arts/design             # Graphic, product, UI/UX design
applied-arts/architecture       # Architecture
applied-arts/fashion            # Fashion design
applied-arts/photography        # Applied/commercial photography
applied-arts/craft             # Applied crafts
```

### fine-arts/

```
fine-arts/painting              # Painting
fine-arts/sculpture             # Sculpture
fine-arts/music                # Music
fine-arts/dance                # Dance
fine-arts/theater              # Theater performance
fine-arts/film                 # Cinema
fine-arts/photography          # Art photography
fine-arts/critique             # Art criticism
```

### literature/

**Second level organized by genre/movement/style for creative works, or by literary study approach**

```
literature/fiction              # General fiction, novels
literature/poetry              # Poetry
literature/drama               # Drama, plays, scripts

# Genres/Styles (creative works)
literature/realism             # Realist literature
literature/romanticism         # Romantic literature
literature/modernism           # Modernist literature
literature/postmodernism       # Postmodernist literature
literature/magical-realism     # Magical realism
literature/gothic              # Gothic literature
literature/sci-fi              # Science fiction literature
literature/fantasy             # Fantasy literature
literature/mystery             # Mystery, detective fiction

# Literary Studies (critical/analytical works)
literature/critique            # Literary criticism
literature/theory              # Literary theory
literature/comparative         # Comparative literature
literature/narratology         # Narratology, narrative theory
```

**Usage guideline**:

- Creative works → Use genre/movement (e.g., `literature/modernism`)
- Critical/analytical works → Use study approach (e.g., `literature/critique`, `literature/theory`)
- When uncertain about specific genre/movement → Use general form (e.g., `literature/fiction`, `literature/poetry`)

### life-practice/

```
life-practice/gastronomy            # Cooking, recipes, restaurant reviews
life-practice/consumption           # Product reviews, shopping, consumerism
life-practice/dwelling             # Housing, interior, gardening
life-practice/health               # Daily health (non-medical)
life-practice/fitness              # Exercise, sports
life-practice/finance              # Personal finance
life-practice/relationships        # Interpersonal relationships
life-practice/parenting            # Parenting, childcare
life-practice/travel               # Travel, tourism
```

### history/

**Reorganized to avoid duplication across other domains**

```
history/ancient                 # Ancient history (pre-500 CE)
history/medieval                # Medieval history (500-1500 CE)
history/modern                  # Modern history (1500-1900)
history/contemporary            # Contemporary history (1900+)
history/local                   # Local/regional history
history/thematic                # Thematic history (intellectual, scientific, etc.)
history/biography               # Historical biographies
```

**Key principle**: Use `history/` for historical studies. For contemporary subjects, use their domain (e.g., current politics → `social-science/politics`, not `history/`)

### linguistics/

```
linguistics/phonetics           # Phonetics, phonology
linguistics/syntax              # Syntax
linguistics/semantics           # Semantics
linguistics/pragmatics          # Pragmatics
linguistics/comparative         # Comparative linguistics
linguistics/applied             # Applied linguistics, language teaching
linguistics/historical          # Historical linguistics
```

## Domain Boundaries & Special Cases

### psychology/ vs psychoanalysis/

- **psychology/**: Scientific, empirical approaches to studying mind and behavior
- **psychoanalysis/**: Psychoanalytic theory, unconscious processes, therapeutic practice based on psychoanalytic tradition

### religion/ vs occultism/

- **religion/**: Organized religions, theology, religious practices
- **occultism/**: Esoteric, mystical, and occult traditions (often outside mainstream religion)

### psychology/ vs medical-science/psychiatry

- **psychology/**: Non-medical study of mind and behavior
- **medical-science/psychiatry**: Medical treatment of mental disorders

### philosophy/mind vs psychology/

- **philosophy/mind**: Philosophical questions about consciousness, mental states
- **psychology/**: Empirical study of mental processes and behavior

### history/thematic vs domain-specific history

Use `history/thematic` for:

- History of science → `history/thematic` (not `natural-science/history`)
- History of philosophy → `history/thematic` (not `philosophy/history`)
- Intellectual history → `history/thematic`

This avoids creating "/history" subdivisions under every domain.

## Tagging Workflow

1. **Identify content subject**: What is this primarily about?
2. **Determine domain**: Which Level 1 category matches the subject?
3. **Assess specificity**: Can you confidently identify the subdomain?
4. **Assign tag**:
    - Confident → Full path: `domain/subdomain`
    - Uncertain → Top-level: `domain`
5. **Validate**: Does this help retrieval? Is it the most accurate fit?

## Common Tagging Scenarios

### Scenario 1: Political Commentary Article

**Content**: Opinion piece on recent election  
**Tag**: `social-science/politics`  
**Reasoning**: Classify by CONTENT (politics), not form (article/commentary)

### Scenario 2: Restaurant Review

**Content**: Review of a local restaurant  
**Tag**: `life-practice/gastronomy`  
**Reasoning**: Practical dining experience, part of life practice

### Scenario 3: Smartphone Review

**Content**: Detailed tech review of new phone  
**Tag**: `life-practice/consumption` OR `engineering/information` (if highly technical)  
**Reasoning**: Consumer-focused → life practice; Engineering-focused → engineering

### Scenario 4: Film Criticism

**Content**: Analysis of a movie's artistic techniques  
**Tag**: `fine-arts/critique` OR `fine-arts/film`  
**Reasoning**: Artistic criticism belongs in fine arts

### Scenario 5: Modernist Novel

**Content**: James Joyce's "Ulysses"  
**Tag**: `literature/modernism`  
**Reasoning**: Creative work tagged by literary movement/style

### Scenario 6: Literary Theory Book

**Content**: Book on narratology  
**Tag**: `literature/narratology` OR `literature/theory`  
**Reasoning**: Literary studies work

### Scenario 7: Psychoanalytic Case Study

**Content**: Freudian analysis of a patient  
**Tag**: `psychoanalysis/freudian`  
**Reasoning**: Psychoanalytic practice and theory

### Scenario 8: Religious Text Commentary

**Content**: Commentary on Buddhist sutras  
**Tag**: `religion/buddhism`  
**Reasoning**: Religious studies content

### Scenario 9: Tarot Guide

**Content**: Book on tarot card reading  
**Tag**: `occultism/divination`  
**Reasoning**: Divination practice within occultism

### Scenario 10: History of Science

**Content**: Book on scientific revolution  
**Tag**: `history/thematic`  
**Reasoning**: Historical study of intellectual/scientific development

### Scenario 11: Cognitive Science Paper

**Content**: Research on memory formation  
**Tag**: `psychology/cognitive`  
**Reasoning**: Scientific psychological research

### Scenario 12: Philosophy of Mind Essay

**Content**: Essay on consciousness  
**Tag**: `philosophy/mind`  
**Reasoning**: Philosophical inquiry, not empirical psychology

### Scenario 13: Travel Essay

**Content**: Personal travel narrative  
**Tag**: `life-practice/travel`  
**Reasoning**: Non-fiction prose classified by content

### Scenario 14: Scientist Biography

**Content**: Biography of Einstein  
**Tag**: `history/biography` OR `natural-science/physics`  
**Reasoning**: Can use either depending on emphasis

### Scenario 15: Contemporary Politics

**Content**: Analysis of current political situation  
**Tag**: `social-science/politics`  
**Reasoning**: Current events → use domain, not `history/contemporary`

## Edge Cases

### Cross-disciplinary Content

When content genuinely spans multiple domains, choose the PRIMARY focus:

- "Philosophy of Religion" → `philosophy/` OR `religion/` (judge by approach)
- "History of Psychoanalysis" → `history/thematic` OR `psychoanalysis/` (judge by emphasis)
- "Bioethics" → `philosophy/ethics` OR `medical-science/` (judge by approach)
- "Psychology of Religion" → `psychology/` OR `religion/` (judge by primary methodology)

### Uncertain Subdomain

When subdomain is unclear, use top-level:

- Political content but unclear aspect → `social-science/politics` OR just `social-science`
- General philosophy introduction → `philosophy`
- Mixed literary genres → `literature`

### Historical vs Contemporary

- Historical study → `history/[period]` or `history/thematic`
- Contemporary topic → Use domain (e.g., `social-science/politics`)
- Biography of historical figure → `history/biography`
- Biography of living person → Relevant domain

## Tag Expansion Guidelines

Before creating new subdomains:

- Verify alignment with library classification standards
- Ensure 5+ items warrant the subdivision
- Check it doesn't overlap with existing subdomains
- Maintain mutual exclusivity with sibling categories
- Document the new subdomain clearly

## Common Mistakes to Avoid

❌ **Mixing form and content**: "This is an essay, so literature" → NO, classify by content  
❌ **Over-specificity**: Creating three-level tags → Stop at level 2  
❌ **Form-based tags**: "review", "essay", "article" as primary classification → Classify by content domain  
❌ **Redundant tagging**: Using both `social-science` AND `social-science/politics` → Use specific only  
❌ **Wrong literature usage**: Political essay as literature → NO, use `social-science/politics`  
❌ **Historical confusion**: Current events as history → NO, use relevant domain; history is for historical studies  
❌ **Domain duplication**: Creating `natural-science/history` → NO, use `history/thematic`

## Summary: Classification Logic

|Content Type|Classification Logic|Example Tag|
|---|---|---|
|Political essay|By subject (politics)|`social-science/politics`|
|Product review|By practical domain|`life-practice/consumption`|
|Film critique|By art form|`fine-arts/critique`|
|Modernist novel|By literary movement|`literature/modernism`|
|Literary theory|By critical approach|`literature/theory`|
|Psychoanalytic work|By psychoanalytic school|`psychoanalysis/[school]`|
|Religious text|By religion|`religion/[religion]`|
|Occult practice|By occult tradition|`occultism/[tradition]`|
|Psychology research|By subfield|`psychology/[subfield]`|
|Travel writing|By practical domain|`life-practice/travel`|
|Biography|By subject's field or period|`history/biography` or domain|
|History of X|By historical approach|`history/thematic`|

## Key Principle

**Always classify by WHAT THE CONTENT IS ABOUT, not HOW IT IS WRITTEN.**

- Writing style (essay, article, review, commentary) does NOT determine classification
- Subject matter and knowledge domain DO determine classification
- For literature: creative works by genre/movement; critical works by study approach
- Historical studies use `history/`; contemporary topics use their domain