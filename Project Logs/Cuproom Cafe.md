# Project Log: Cuproom Cafe

## What Worked

- Keeping the hero mostly untouched was the right call. It already had the right mood, so the work was about polishing around it, not replacing it.
- The menu became much stronger after moving away from a bulky content-section feel into a cleaner cafe menu structure with tabs, product names, prices, and subtle connector lines.
- Reducing menu tabs to four worked well:
  - Kava
  - Matcha ir salti gerimai
  - Arbata ir kakava
  - Kepiniai / desertai
- The reviews section worked because it used real Google review content, simple cards, and a clear "Atsiliepimai" title without extra marketing copy.
- The language toggle design became much better after focusing on soft physical motion instead of a mechanical slide.
- Small page-load and scroll animations improved the perceived quality without turning the site into an animation demo.
- The warmer dark gallery background direction worked better than pure obsidian black for Cuproom because the brand is cozy, not luxury-dark.

## What Failed

- Fading the whole `main` / `footer` on language switch caused a cream or white flash. The correct approach was text-only fading.
- Re-rendering gallery images on language change caused photos to animate even though the user only changed language. Images should stay anchored.
- Some AI/Google suggestions were too dramatic for the brand, especially full black luxury styling. Cuproom needs warmth and softness.
- Broad changes created risk. This project showed again that small targeted improvements beat redesigning whole sections when the base is already working.
- Copy that explains too much often weakens the design. The gallery intro sentence was unnecessary and made the page feel less elegant.

## What User Liked

- Warm cream, cocoa, and sage palette.
- Editorial serif headings paired with clean sans-serif body text.
- Calm, useful animations: fade, slight lift, button response, soft language transition.
- Real photos and real reviews over generic stock-like polish.
- Menu items displayed like an actual cafe menu, with prices easy to scan.
- Simple section titles:
  - Atsiliepimai
  - Galerija
  - Musu meniu
  - Kur mus rasti
- Trust-building details that feel real, not decorative.
- Layouts that leave breathing room without becoming empty.

## What User Rejected

- Heavy luxury-black sections when they feel disconnected from the cafe brand.
- Extra explanatory paragraphs when the section already makes sense.
- Rebuilding or redesigning entire sections when only one detail needs fixing.
- Fake-looking review cards, generic icons, or generic profile placeholders when real review screenshots/content exist.
- Animations that affect images or layout during a language switch.
- Buttons or pill labels that look clickable but do nothing.
- Duplicate CTAs that perform the same action.
- AI-style dramatic copy when simple local-business clarity is stronger.

## Technical Issues

- Language switching should animate text only.
- Gallery DOM should not be rebuilt on language change. Update image `alt` attributes only.
- Hero text may need a targeted language-transition selector because hero entrance CSS can override general text fading.
- Do not fade whole page containers for language changes.
- Do not call large reveal animations again just because language changed.

## Rules To Reuse

- Do not redesign the whole site unless explicitly asked. Preserve what already works.
- When changing language, animate text only. Do not fade whole sections and do not rebuild image DOM.
- Images should move only when the interaction is about images, not when text changes.
- For cozy local cafes, use warmth, texture, real details, and restraint. Avoid forcing luxury-dark aesthetics.
- If a section feels flat, first try a subtle tone shift from the existing palette before jumping to black.
- Real business websites need trust before spectacle: real photos, real reviews, clear menu, clear address, clear hours.
- Keep section copy minimal. If a title is enough, do not add a paragraph just because there is space.
- Use animations as signs of care, not as the main event.
- Before implementing Google/AI suggestions, translate them into the brand's actual personality.
- Always protect the user's existing design direction. The job is companion and editor, not bulldozer.

## Rules Not To Overgeneralize

- Dark gallery sections can work, but the exact darkness must fit the brand. Cuproom needed cocoa warmth, not Solt-style obsidian.
- Real Google review content is useful, but it must be presented with care and not made to look fake or over-designed.
- Minimal copy is powerful, but not every section should become silent. Use copy when it clarifies action, trust, or context.
