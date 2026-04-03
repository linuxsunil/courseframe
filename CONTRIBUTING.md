# Contributing to CourseFrame

First off — thank you. CourseFrame exists for the global L&D community and every contribution, big or small, makes it better for thousands of instructional designers.

---

## What we need most

- **New block types** — got a Rise block we haven't covered? Build it.
- **Bug reports** — something broken in your browser or with a specific AI provider?
- **UI improvements** — the interface can always be cleaner, clearer, faster.
- **Documentation** — better explanations, use case examples, language translations.
- **Workflow ideas** — how are you using CourseFrame? Share it as a discussion.

---

## Ground rules

- CourseFrame must remain a **single HTML file**. No build tools, no npm, no frameworks. This is intentional — the zero-install requirement is a core feature, not a constraint to work around.
- All interactivity must be **vanilla JavaScript**. No jQuery, no React, no libraries.
- Any new feature must work **without an API key** (manual mode must always be viable).
- Keep the exported file **self-contained** — no external CDN calls, no runtime dependencies.
- Write code that a non-developer instructional designer can read and understand.

---

## How to contribute

### Reporting a bug

1. Check [existing issues](https://github.com/linuxsunil/courseframe/issues) first
2. Open a new issue with:
   - What you expected to happen
   - What actually happened
   - Your browser and OS
   - Which AI provider you were using (if relevant)
   - Steps to reproduce

### Suggesting a feature

Open an issue with the `enhancement` label. Describe:
- What problem it solves for an instructional designer
- How you imagine it working
- Whether it fits the single-file constraint

### Submitting a pull request

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature-name`
3. Make your changes to `index.html`
4. Test in Chrome, Firefox, and Safari
5. Test both AI mode and Manual mode
6. Test the exported HTML file in a browser with no internet connection
7. Open a pull request with a clear description of what changed and why

---

## Adding a new block type

Each block type needs four things:

1. **A default object** in the `defaults` map inside `addBlock()`
2. **An editor UI** in `renderBlockEditor()` — what the ID sees when building
3. **A preview renderer** in `renderRiseBlock()` — what it looks like in the Rise preview
4. **An export renderer** inside `exportHTML()` — the standalone HTML version

Follow the existing patterns for any of the 11 current block types. The `quiz` block is the most complex reference; `callout` is the simplest.

---

## Code style

- 2-space indentation
- Descriptive function names over comments
- No semicolons on standalone lines (they're used inline in minified export code only)
- CSS variables for all colours — never hardcode hex values in the app shell
- Keep the file under 150kb unminified

---

## Questions?

Open a [discussion](https://github.com/linuxsunil/courseframe/discussions) — happy to help you get started.
