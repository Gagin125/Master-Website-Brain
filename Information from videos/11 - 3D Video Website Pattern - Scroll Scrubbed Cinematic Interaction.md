# 11 - 3D Video Website Pattern - Scroll Scrubbed Cinematic Interaction

Source video: https://youtu.be/IeR5ZMKssSc?si=fZwpo_V_GNFYY1Kj  
Local video inspected: `C:\Users\Dovydas\Downloads\videoplayback (21).mp4`  
Transcript inspected: `C:\Users\Dovydas\.codex\attachments\48b7297a-d619-45bd-beae-86e01a6524d0\pasted-text.txt`  
Frame sheet: `.video_frames/video-11-3d-website/contact_sheet.jpg`

## Core Idea

This video is less about building true interactive 3D with WebGL and more about creating a 3D-feeling cinematic website from generated motion assets.

The system is:

1. Start with a strong visual reference.
2. Generate or remix a still image that matches the intended brand.
3. Turn that still into a short animated video.
4. Place the video inside a minimal editorial website.
5. Tie video playback and typography movement to scroll.
6. Add section transitions that feel spatial, not just stacked.

The important lesson is not "use AI videos everywhere." The useful pattern is: build a strong art-directed motion asset first, then let the website structure stay restrained so the motion has room to carry the experience.

## What The Website Visually Does

- Uses a dark, almost pure-black canvas to make animated objects feel luminous and cinematic.
- Keeps navigation extremely minimal so the motion asset is the focal point.
- Uses oversized typography that fills the screen width.
- Places hero text low in the viewport or across the full hero width instead of using a normal centered SaaS headline block.
- Uses scroll-scrubbed animation, so motion follows the user's hand rather than playing on a timer.
- Lets text characters fall, fade, squash, or disappear progressively as the user scrolls.
- Brings later panels upward from the bottom of the viewport, making the page feel like a staged scene.
- Combines video backgrounds with 3D-like text effects such as circular text drums, depth, blur, opacity falloff, and keyword emphasis.

## Design Thinking Behind It

The page works because the structure is simple enough to let the motion feel premium.

The creator does not add many visual ideas at once. The page uses:

- one dark stage,
- one hero motion object,
- one oversized title,
- one clear scroll behavior,
- one next section transition.

That restraint is what makes the result feel like a cinematic experience instead of a noisy effects demo.

The video also shows that the "3D" feeling often comes from choreography, not from the technology itself. A generated video, a scroll timeline, and careful typography can create enough spatial emotion without loading a heavy 3D engine.

## Practical Build Pattern

### Hero

- Full viewport height.
- Pure black or deep neutral background.
- Minimal navigation.
- One oversized headline.
- Motion asset placed behind or beside the headline.
- Video element muted, inline, and preferably short.
- Scroll drives `currentTime` or a timeline that syncs with the video.

### Typography

- Choose font before adding complex motion.
- Big display type does most of the visual work.
- Fit the headline to the viewport width, but keep it readable.
- Split headline into characters or words only if the animation actually supports the concept.
- Use scroll-linked animation for reversible motion.

### Video Motion

- Keep video loops short when used as a scroll-scrubbed asset.
- Match the generated video duration to the intended scroll interaction.
- Use the same first frame as the poster image to avoid a jarring load flash.
- Compress video for web. The creator explicitly notes that 1080p is usually more practical than 4K for websites.
- Use `muted`, `playsinline`, and preload carefully.

### Section Transitions

- Do not just stack sections normally if the page is selling an immersive concept.
- Let panels rise, pin, reveal, or cover the previous section.
- Use rounded edges or large soft section entrances only when they match the brand.
- Keep each section's motion concept distinct but related.

## Scroll-Scrubbed Video Implementation Pattern

Use this when the video is meant to respond directly to scroll:

1. Preload enough metadata to know video duration.
2. Map scroll progress from 0 to 1.
3. Set `video.currentTime = progress * video.duration`.
4. Use `requestAnimationFrame` or a motion library to smooth updates.
5. Do not autoplay the same video independently if scroll controls it.
6. Test on mobile because frame seeking can be uneven on weaker devices.

Important: scroll-scrubbing video can feel premium when smooth, but it can also become heavy. For client work, test on a real phone early.

## When This Pattern Is Worth Using

Use this for:

- creative agencies,
- motion studios,
- fashion/editorial brands,
- product launches,
- entertainment projects,
- 3D-heavy portfolios,
- premium hero concepts where atmosphere matters,
- websites where the site itself is meant to be a visual proof of skill.

Use it carefully for:

- restaurants,
- hotels,
- luxury local businesses,
- event venues.

For these, one cinematic hero video or one controlled immersive section can work. The full scroll-scrubbed 3D treatment may be too much if the main user goal is menu, booking, contact, or trust.

Avoid it for:

- SEO-first local service sites,
- sites with mostly older mobile users,
- urgent conversion pages,
- pages where speed matters more than spectacle,
- businesses without strong visual assets.

## Performance Rules

- Short video beats long video.
- 1080p usually beats 4K for websites.
- Use a poster frame extracted from the actual video.
- Compress aggressively, but avoid visible artifacting in hero sections.
- Lazy-load non-hero motion assets.
- Do not initialize complex scroll animations before the first meaningful content is visible.
- Respect `prefers-reduced-motion`.
- Keep fallback static images for devices where video or scroll-scrubbing fails.
- Check mobile load time before showing a client.

## UX Rules

- Motion should support orientation, not confuse it.
- If scroll controls animation, the user should feel in control.
- Avoid animations that delay access to important information.
- Keep CTAs available and legible.
- Do not make every section a motion event; the user needs rest.
- If the first screen is cinematic, the next section should clarify value quickly.

## Prompting Pattern Extracted From The Video

The creator's useful prompting method:

1. Describe the layout in plain spatial terms.
2. Specify exact viewport behavior.
3. Specify typography placement.
4. Specify scroll behavior separately.
5. Add animation physics after the static layout works.
6. Iterate with small corrections instead of asking for the whole perfect website in one prompt.

Example prompt structure:

```text
Create a 100vh hero section with a pure black background.
Place a minimal navbar at the top.
Place a large uppercase headline at the bottom, filling the full viewport width.
Split the headline into characters.
On scroll, each character falls downward and fades out from left to right.
Tie the animation to scroll progress so scrolling back reverses it.
```

This is more reliable than asking for "make an award-winning animated 3D website."

## What To Add To Future AI Website Prompts

For a 3D-feeling hero:

- define the visual object,
- define the background mood,
- define whether the asset is true 3D, generated video, or normal video,
- define how scroll affects it,
- define fallback behavior,
- define mobile behavior,
- define performance constraints.

Useful sentence:

> Use cinematic motion only where it increases brand perception; keep conversion sections calm, readable, and fast.

## What Not To Copy Blindly

- Do not copy the exact black-background sci-fi style for every brand.
- Do not turn every page into a scroll animation demo.
- Do not assume generated video equals premium design.
- Do not use 3D motion when the business has no reason for it.
- Do not let AI decide fonts randomly; the video itself says font choice is a major part of the design.
- Do not skip manual visual direction. The creator repeatedly guides, replaces, adjusts, and checks the output.

## How We Could Implement This In Our Work

For a restaurant:

- Use one cinematic hero video, not a full 3D scroll system.
- Use a real food, cocktail, chef, or interior asset.
- Keep menu, reviews, location, and booking sections fast and normal.
- Use motion as atmosphere, then return to clarity.

For a creative agency:

- Use scroll-scrubbed video or WebGL as proof of capability.
- Let the site itself demonstrate motion taste.
- Use section reveals and typography choreography more aggressively.

For a product site:

- Use true 3D only if users benefit from inspecting the product.
- Otherwise use generated video or pre-rendered motion for speed.

## Reusable Rule

3D is not automatically premium. Spatial intent is premium.

If the visitor understands the brand better because the motion exists, use it. If the motion only says "look what I can do," simplify it.
