# 06 - Award Style Animated Figma Website - Extracted Principles

Source video: https://youtu.be/JXlwfKpDwDI?si=ab37XkdIo8TS-0iF  
Local video: `C:\Users\Dovydas\Downloads\Design Award-Winning Websites in Figma _ Complete Animation Tutorial.mp4`  
Transcript: `C:\Users\Dovydas\.codex\attachments\d595a2d8-5afe-4551-94cc-073580bb8119\pasted-text.txt`

## Core Lesson

Award-style animated websites are not created by adding motion after a static layout is finished.

They are built by planning:

- the story sequence,
- the visual hero object,
- the section order,
- the separable asset layers,
- the before and after states,
- and the final way the design will be presented to a client or developer.

The animation works because the design was built to be animated from the start.

## The Process

### 1. Start with information architecture

Before designing, decide the page structure.

In the video, the cafe website is planned around:

- hero section,
- selling point section,
- menu section.

This matters because the animation needs a narrative path. If the sections are random, the motion becomes random too.

Reusable rule:

> First define the website story. Then design the sections. Then animate the transitions.

### 2. Choose the visual hero object early

The designer starts with the product/cup mockup because the entire layout is built around it.

For a cafe, the hero object is the cup/product. For another business, the hero object could be:

- a product,
- a food dish,
- a bottle,
- a tool,
- a physical location,
- a person,
- a dashboard,
- a machine,
- a room,
- or another brand-specific object.

Reusable rule:

> Award-style visual sites need a main object that can carry the composition and motion.

### 3. If the client has weak photos, create or source better visual material

The designer uses mockups and customizes them with brand visuals.

This is useful when:

- the business has no professional product shots,
- the product is not photographed cleanly,
- the hero needs a more polished, campaign-like visual,
- or the animation requires a controllable object.

But for real business trust, real assets are still better when available.

Use mockups carefully:

- OK for concept/demo work.
- OK when clearly used as product visualization.
- Risky if it misrepresents the real product or space.

### 4. Separate assets into layers before designing motion

The designer exports each product/cup as its own PNG layer.

Reason:

- one flat image cannot animate convincingly,
- separate objects can move independently,
- shadows can be controlled,
- depth can be created,
- product objects can travel between sections.

Reusable rule:

> If something needs to move, it must exist as its own layer.

### 5. Design the layout around the product composition

Once the product objects are placed, the designer designs around the empty spaces.

The hero layout is not made from a generic template. It is composed around:

- where the cups sit,
- where empty space appears,
- where text can breathe,
- where the CTA belongs,
- where small brand details can add personality.

This is why the layout feels custom.

Reusable rule:

> Do not place assets into a pre-made layout. Let strong assets shape the layout.

### 6. Use a grid, but do not let the grid make the design boring

The designer adds a 12-column grid with margins and gutters.

The grid gives structure, but the visual interest comes from:

- asymmetrical product placement,
- oversized typography,
- custom stickers,
- controlled depth,
- object layering,
- and animated continuity.

Reusable rule:

> Use the grid for discipline, then use art direction to make the page memorable.

### 7. Create realistic depth manually

Instead of relying only on default drop shadows, the designer draws custom shadow shapes under the products, blurs them, lowers opacity, and places them behind the objects.

This makes the mockups feel like they belong in the same environment.

Reusable rule:

> Cheap shadow: generic drop shadow. Premium shadow: shaped, blurred, directional, and connected to the object.

### 8. Make visual personality intentional

The designer adds custom stickers/illustrations after the core layout works.

They are not the foundation. They are final personality accents.

Good use:

- fills dead space,
- supports cafe/playful brand tone,
- creates a memorable visual system,
- gives the page handcrafted character.

Bad use:

- random decoration,
- trend-based clutter,
- icons that look like buttons,
- visuals that do not match the brand tone.

Reusable rule:

> Personality details should support the brand, not compete with the message.

### 9. Design fold by fold

The designer thinks in scroll folds:

- first fold: hero,
- second fold: selling point,
- next fold: menu.

This prevents awkward sections that are split halfway across the viewport.

Reusable rule:

> Design the scroll journey as a sequence of deliberate viewports, not as a long page of unrelated blocks.

### 10. Turn the selling point into a visual event

The second section is built around a big statement:

> We use premium fresh beans and fresh ground spices.

Instead of adding another generic card row, the designer makes the claim itself the visual centerpiece.

He then inserts small image windows into the typography and brings one product object into the section.

Reusable rule:

> Important brand claims deserve visual treatment. Do not bury them in body copy.

### 11. Animation is a before state and an after state

The video explains animation as:

- before state,
- after state,
- transition between them.

In Figma, Smart Animate interpolates between matching layers across frames.

This simple idea is powerful:

- move object from A to B,
- scale object from small to full size,
- change opacity from 0 to 1,
- rotate slightly,
- move text into position,
- move product from hero into next section.

Reusable rule:

> For every animation, define the exact before state and after state.

### 12. Animate the page entrance in layers

The designer creates a page load sequence:

- cups appear first,
- UI/header elements follow,
- text appears,
- stickers scale in,
- CTA enters.

This creates hierarchy. The user does not receive everything at once.

Reusable rule:

> Entrance animations should reveal importance order, not just “make everything move.”

### 13. Use product continuity between sections

One cup from the hero moves down into the next section while other hero elements scroll away.

This makes the scroll feel like one continuous story instead of separate static blocks.

Reusable rule:

> If a product or brand object appears in the hero, consider letting it travel into the next section.

### 14. Prototype motion to communicate intent

The designer records the Figma prototype because the animation is part of the design.

This helps:

- clients understand the final experience,
- developers understand the intended behavior,
- portfolio viewers see the site as alive,
- social media posts feel more premium.

Reusable rule:

> For motion-heavy work, do not only deliver static screens. Deliver a motion reference.

### 15. Polish the presentation

The video uses OBS/screen recording and After Effects to present the prototype:

- crop the recording,
- place it in a shaped frame,
- add rounded corners,
- add background color or image,
- add subtle shadow/glow,
- export for social/client presentation.

This is not the website itself. It is sales/presentation polish.

Reusable rule:

> A great design shown badly feels weaker. Presentation is part of perceived quality.

## What Codex Can Apply Later

Codex can help by:

- planning the section story before implementation,
- defining the hero object and how it moves,
- identifying which assets must be separate layers,
- writing animation specs with states, durations, easing, and triggers,
- implementing the motion in CSS/JS/GSAP when appropriate,
- creating developer notes from Figma-style motion logic,
- deciding when motion is useful and when it is wasteful,
- turning a static page into a scroll story without destroying performance.

## What The Human/User May Need To Provide

The user/client may need to provide:

- real product photos,
- video footage,
- brand logo,
- menu/content,
- approval for mockup use,
- high-resolution images,
- preference for brand mood,
- the real business goal.

For an award-style animated website, the most important user-provided asset is often a strong hero visual.

## Where This Approach Fits

Best for:

- product landing pages,
- cafes/restaurants with strong visual assets,
- creative portfolios,
- premium brand launches,
- campaign pages,
- hospitality pages,
- fashion/beauty/lifestyle brands,
- sites where atmosphere and memorability matter.

Use carefully for:

- local service businesses,
- SEO-heavy sites,
- sites where users mainly need fast information,
- medical/legal/financial pages,
- businesses with weak imagery.

The motion should never block clarity, speed, accessibility, or conversion.

## Mistakes To Avoid

- Designing a generic page first and trying to “award animate” it later.
- Using one flattened hero image when objects need to move independently.
- Adding motion without a story reason.
- Letting stickers and illustrations become random clutter.
- Making the animation more memorable than the offer.
- Ignoring performance when translating Figma motion into a real website.
- Presenting Figma prototype behavior as if it automatically equals production behavior.
- Using fake product imagery on a real business site without approval.

## Practical Checklist

- Define the section story before designing.
- Pick the main visual object.
- Gather or create high-quality visual assets.
- Separate moving elements into layers.
- Build the hero around the object, not around a generic template.
- Use a grid for structure.
- Add custom shadows for depth.
- Add brand personality details only after the core layout works.
- Design fold by fold.
- Turn key selling points into visual events.
- Define before and after states for every motion.
- Animate entrance hierarchy.
- Use object continuity between sections.
- Prototype the animation.
- Record/present the motion cleanly.
- Rebuild production motion responsibly with performance and accessibility in mind.

