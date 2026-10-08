# Project tracker maintenance

This repository's public progress tracker is the static site in `site/`. Its source data is `site/progress.json`; the display is implemented in `site/index.html` and `site/project.html`.

## Updating project information

- Keep `site/progress.json` valid JSON. Preserve stable `id` values because they are used in shareable detail-page links.
- Use plain, player-friendly language. Explain unfamiliar game or technical terms briefly rather than assuming visitors know them.
- Treat the local planning workbook (`..\ash_tasks\XL_planning_sheets.xlsx`, when available) as a long-term wishlist, not proof that a feature is being worked on or will ship. The Nobuyuki Sanada outfit is the main character focus recorded so far.
- Only describe work as active, ready to try, or complete when recent project notes support that status. Progress percentages are rough estimates; update them only when there is a clear reason and never describe them as measured completion.
- Keep new character and outfit slot capacity separate from creating new characters or outfits. The capacity work has three smaller areas: character spaces, character-select categories, and outfit spaces.
- Add new areas as top-level `streams`; add related smaller steps to that area's `substreams`. Give each one a stable lowercase-hyphenated `id`, valid `state`, integer `progress` from 0 to 100, player-friendly `summary` and `activity`, and a longer `description`.
- Write `activity` as a neutral description of current work, never an instruction for the reader. Use present-tense wording such as "Finalizing the work on Nobuyuki." The site labels it "Ongoing:", "Planned:", "Ready to test:", or "On hold:" based on the item's state.
- Add a dated, short entry to `updates` when recording a meaningful change.

## Screenshots and privacy

- Add only selected, public-ready screenshots to `site/assets/screenshots/` and reference them in the matching item's `screenshots` array as `{ "src": "assets/screenshots/example.png", "alt": "What the image shows", "caption": "A short explanation" }`.
- Never publish game installation files, extracted game assets, save files, private local paths, credentials, or material the project does not have permission to share.
- Do not publish wireframes, debug overlays, diagnostic montages, or other development-only images as player screenshots. If unsure whether an image is safe and suitable to publish, ask the user first.
- A public issue or image link is a suggestion only. Review and select images before adding copies to the site; opening an issue does not update the tracker automatically.

## Publishing

Check that the JSON parses and that all detail links use valid IDs. Changes pushed to `main` are published by the GitHub Pages workflow. Do not push or publish without the user's approval.
