# Refactoring UI - Extracted Principles

Source: Steve Schoger and Adam Wathan, *Refactoring UI*

Extraction quality: usable. The PDF text extraction was strong enough to capture the practical interface principles.

## Core Idea

Good UI is not created by randomly adding visual style. It is created by building hierarchy, spacing, contrast, constraints, and systems.

This source is especially useful for turning rough AI-generated layouts into polished interfaces.

## Key Principles

### 1. Start with the feature, not the shell

Do not begin by designing the whole app or page wrapper. Begin with the actual thing the user needs to do.

Website translation:

- for a restaurant, start with booking, menu, location, proof
- for a cafe, start with menu, atmosphere, directions, social proof
- for SaaS, start with the core task or feature workflow

A beautiful shell around an unclear feature is still weak design.

### 2. Low-fidelity design prevents premature polish

Designing in grayscale first forces hierarchy, spacing, and contrast to carry the interface before color enters.

This is a useful AI-agent rule:

Before choosing palette, prove the layout works in structure.

### 3. Hierarchy is everything

Visual hierarchy determines what feels important.

Hierarchy is controlled through:

- size
- weight
- contrast
- spacing
- color
- position
- grouping
- de-emphasis

If everything competes for attention, nothing wins.

### 4. Emphasize by de-emphasizing

Not every element needs to become louder. Often the better move is to make secondary elements quieter.

Examples:

- make meta text smaller/lighter
- reduce border contrast
- move secondary CTAs into simpler styling
- make support copy quieter than headings
- reduce visual weight of decorative details

### 5. Use a spacing and sizing system

Do not tweak every value by feeling. Use a constrained scale.

Website translation:

- section padding scale
- card padding scale
- button sizes
- type scale
- image frame ratios
- gap values

This reduces inconsistency and makes the design feel intentional.

### 6. Avoid ambiguous spacing

Spacing communicates relationships.

If spacing is ambiguous, users cannot tell what belongs together.

Examples:

- heading should sit closer to its paragraph than to the previous section
- product price should visually belong to product name
- CTA should be separated enough to feel like an action
- gallery items should have consistent gaps

### 7. Grids are useful, but not everything

The source warns against treating grids as a magic answer.

The better rule:

Use grids to create order, but solve the actual hierarchy and relationship problems directly.

### 8. Color should not carry meaning alone

Use more than color for states and meaning:

- text labels
- icons
- borders
- position
- typography
- patterns

This matters for accessibility and clarity.

### 9. Depth must serve elevation

Shadows and depth should communicate layering, not decoration.

Bad:

- random heavy shadows
- everything floating
- fake depth everywhere

Good:

- subtle elevation for overlays
- depth to separate sticky nav or modal
- consistent shadow logic

### 10. Borders are often overused

Interfaces can often feel cleaner by using:

- background contrast
- spacing
- shadows
- subtle dividers
- typographic grouping

instead of boxing everything with borders.

## Website Translation

### Buttons

- Primary buttons should use consistent color.
- Hover should feel responsive but not loud.
- Button text should be action-specific.
- Do not use multiple primary styles in the same section.

### Forms

- Use clear labels.
- Provide error feedback near the problem.
- Make fields look editable.
- Avoid relying on placeholder-only labels.

### Cards

- Use cards only when framing helps.
- Avoid cards inside cards.
- Keep radius and borders consistent.
- Do not make whole page sections into decorative cards unless the tool itself is framed.

### Typography

- Use smaller headings inside compact surfaces.
- Keep body text readable.
- Do not make display type do body-copy work.
- Use letter spacing mostly for small uppercase labels, not normal paragraphs.

## Common AI Website Mistakes

- starting with a pretty page instead of the user's task
- using too many arbitrary colors and shadows
- treating font size as the only hierarchy tool
- making secondary text too loud
- using borders around everything
- creating ambiguous gaps
- inconsistent button heights and radii
- huge decorative cards that do not help usability

## Candidate Rules For The Brain

- Start with the user's task, not the page shell.
- Prove hierarchy before adding color.
- Emphasize important things partly by quieting less important things.
- Use constrained spacing, sizing, and color systems.
- Spacing communicates relationships.
- Depth should explain layering.
- Use fewer borders when spacing and contrast can do the job.

## Rules Not To Overgeneralize

- Do not make every site grayscale or ultra-minimal.
- Do not remove all borders if users need separation.
- Do not over-systematize expressive brand pages.
- Do not mistake polish for strategy.

