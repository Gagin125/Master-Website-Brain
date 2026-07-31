# The Design of Everyday Things - Extracted Principles

Source: Don Norman, *The Design of Everyday Things*

Extraction quality: usable. The PDF text extraction was strong and captured the central concepts clearly.

## Core Idea

Bad user behavior is often bad design. If users click the wrong thing, miss the action, misunderstand the state, or make mistakes, the design probably failed to communicate.

For websites, this means UX is not just visual beauty. It is discoverability, feedback, signifiers, constraints, mappings, conceptual models, and error recovery.

## Key Principles

### 1. Human-centered design starts with people

Design should begin with how people behave, not how the designer wishes they behaved.

For websites:

- users skim
- users guess
- users get distracted
- users use phones
- users misread vague labels
- users abandon when friction feels high

The site must be designed around real behavior.

### 2. Affordances are possible actions

An affordance is what an object or interface allows a user to do.

In web design:

- a button affords clicking
- a form field affords typing
- a menu affords opening
- a carousel affords sliding only if this is signaled

But affordance alone is not enough.

### 3. Signifiers tell users what actions are possible

Signifiers are the visible cues that communicate what can be done.

This matters more than affordance in many interfaces.

Examples:

- button styling
- hover/focus states
- cursor changes
- labels
- arrows
- underline on links
- selected tab states
- disabled states
- progress indicators

If users cannot perceive the signifier, the interaction may as well not exist.

### 4. Feedback confirms action

After a user acts, the interface should respond.

Website examples:

- button hover/press response
- language switch animation
- form success message
- menu expansion state
- loading indicator
- active tab underline
- modal open/close transition

Feedback should be immediate enough to reassure the user.

### 5. Good mapping makes controls feel natural

Mapping is the relationship between control and result.

Examples:

- tab selection changes visible content below
- "View full menu" reveals or navigates to full menu
- language toggle changes visible language and URL state
- "Directions" opens map
- logo returns home/top

Poor mapping causes confusion.

### 6. Constraints prevent errors

Good design limits wrong actions.

Website examples:

- show unavailable menu items clearly
- prevent submitting incomplete forms
- avoid inactive elements that look clickable
- disable impossible states
- keep one primary CTA per decision point

### 7. Error is often a design failure

Users make slips and mistakes. The design should reduce, catch, and recover from them.

Examples:

- wrong language after page navigation
- mobile nav open but options invisible
- button that looks active but does nothing
- videos failing without graceful fallback
- broken gallery/lightbox states

Do not blame users for reasonable misunderstandings.

### 8. Conceptual models help users predict behavior

Users form a mental model of how the site works.

If the site violates that model, trust drops.

Examples:

- same language toggle behavior across pages
- consistent navigation structure
- gallery filters work the same way everywhere
- CTA labels match actual destination
- menu page and homepage menu share logic

## Website Translation

### Navigation

Navigation needs strong signifiers:

- current language visible
- mobile hamburger visibly opens
- close icon visibly closes
- menu items are tappable
- logo behavior is predictable

### Language switching

Language switch should update:

- visible text
- URL parameter
- document language attribute
- page-to-page link behavior
- animation state

Otherwise the conceptual model breaks.

### Video hero

Video background needs:

- poster fallback
- graceful loading
- text contrast
- no layout shift
- CTA clickability

### Forms and CTAs

Every CTA should match the action:

- "Book a table" opens booking
- "View menu" opens menu
- "Read reviews" opens Google reviews
- "Directions" opens maps

No vague labels where the outcome matters.

## Common AI Website Mistakes

- using visual affordances without signifiers
- hiding interactions behind hover effects
- inconsistent states across pages
- not updating URLs when state changes
- no feedback on click or loading
- blaming "user confusion" instead of fixing the interface
- styling decorative elements like controls

## Candidate Rules For The Brain

- If users misunderstand, inspect the design before blaming the user.
- Every interaction needs a perceivable signifier.
- Every action needs feedback.
- State changes should be visible and durable when useful.
- The same pattern should behave the same way across pages.
- Constraints are part of good UX.
- CTAs must map clearly to their result.

## Rules Not To Overgeneralize

- Do not over-explain everything with visible instructional text.
- Do not make every interaction heavy or animated.
- Do not add constraints that block legitimate user paths.
- Do not sacrifice brand mood by making every cue loud.

