# Folder Synthesis - Interactive Layout & User Experience

Sources:
- Steve Krug, *Don't Make Me Think*
- Steve Schoger and Adam Wathan, *Refactoring UI*
- Don Norman, *The Design of Everyday Things*

Purpose: extract reusable UX and interaction principles for later comparison before adding to the active brain.

## The Main Lesson

A website should not merely look premium. It should behave clearly.

The user's next step should feel obvious, the interface should respond when touched, and layout should guide behavior without forcing the user to decode the page.

## Strong Shared Principles

### 1. Clarity beats cleverness at decision points

Creative design is valuable, but not where users need to understand what to do.

Use clarity for:

- navigation
- CTAs
- forms
- menus
- prices
- contact information
- language switching
- booking/directions actions

Use creativity for:

- hero atmosphere
- gallery rhythm
- brand storytelling
- editorial section flow
- subtle microinteractions

### 2. Users scan and satisfice

Users usually do not study the full page. They scan until they find the first reasonable path.

Therefore:

- primary path must be obvious
- headings must carry meaning
- long copy needs structure
- key proof should be easy to notice
- menus and contact sections must be skimmable

### 3. Visual hierarchy is UX, not decoration

Hierarchy tells users what matters.

Strong hierarchy uses:

- size
- contrast
- weight
- spacing
- grouping
- alignment
- color
- de-emphasis

If every element is loud, the user loses the path.

### 4. Signifiers and feedback make interfaces feel alive

Users need to know:

- what can be clicked
- what is selected
- what changed
- whether their action worked

This is where microinteractions matter.

Good microinteractions:

- hover states
- pressed states
- tab underline movement
- language switch fade
- menu open/close motion
- form feedback
- loading fallback

Bad microinteractions:

- animation that hides content
- motion without purpose
- slow interactions that make the page feel delayed
- effects that draw attention away from the action

### 5. Consistency builds a conceptual model

Users learn the site quickly when repeated patterns behave the same way.

Examples:

- language switch works across homepage, menu, gallery
- navigation labels keep meaning
- CTA styles stay consistent
- tabs behave consistently
- mobile menu exposes the same choices users expect

### 6. Design systems reduce accidental inconsistency

A restrained set of values improves quality:

- spacing scale
- type scale
- color roles
- button styles
- border radius
- shadows
- section widths

This is not about making every site look the same. It is about preventing random drift.

## Website-Specific Rules

### Navigation

- Logo should be visually distinct from normal nav links.
- Nav groups should not shift when language changes.
- Mobile nav must clearly expose links and language controls.
- Duplicate CTAs with the same destination should be avoided.
- Logo behavior should match expectation: home/top.

### Language switching

Language switching should:

- update visible text
- update document language
- update URL parameter
- preserve language across internal pages
- use a small fade if text changes visibly
- avoid animating images unnecessarily

### Hero

Hero should:

- answer the core positioning quickly
- keep text contrast strong over video/photo
- avoid too many CTAs
- provide graceful video loading
- avoid awkward line breaks

### Menu

Menu UX should:

- use category tabs that fit
- clearly connect item name and price
- keep typography stable before/after expansion
- make active tab obvious
- preserve language state

### Gallery

Gallery UX should:

- show real assets clearly
- avoid stretching photos beyond useful crop
- use filters only if they are useful
- provide smooth transition without feeling sluggish
- keep page title and nav consistent

### Reviews

Reviews UX should:

- show source clearly
- make translation notes honest but quiet
- provide link to original review source
- avoid fake-looking profile treatments

### Visit / Contact

Contact UX should:

- group address, hours, phone, email, socials together
- map should be visibly connected to directions CTA
- social links should not look like random decoration
- action labels should match the result

## Common AI Agent Mistakes

- redesigning whole sections when only one behavior needed fixing
- adding animation before solving signifiers
- making pretty components that do not communicate state
- using vague CTA labels
- making inactive badges look like buttons
- not testing mobile interaction states
- changing copy/design beyond the requested scope
- forgetting language persistence across pages
- making UX changes that affect layout stability

## Candidate Rules For The Active Brain Later

- Design around the user's next action.
- Do not make users decode the interface.
- Every interactive element needs signifier and feedback.
- Text changes can fade; images should not animate unless the image itself changed.
- Functional content should be more conventional than emotional content.
- State should be consistent across pages.
- Visual hierarchy is a behavioral tool.
- If a user reasonably misunderstands something, the design needs work.

## Tensions To Remember

### Clarity vs brand expression

Brand expression matters, but do not spend it where the user needs certainty.

### Motion vs speed

Motion can make a site feel crafted. Too much motion makes it feel delayed or fake.

### Convention vs distinction

Conventions help users move. Distinction helps users remember.

Use convention for operation, distinction for atmosphere.

## Strongest Current Principle

The page should feel like it understands the visitor's next move.

That means clear structure, obvious actions, honest signifiers, immediate feedback, and enough restraint that the user never has to fight the design to get what they came for.

