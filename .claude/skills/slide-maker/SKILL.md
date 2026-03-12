# Skill: Marp Slide Maker

## Overview

This skill generates presentation slides from Markdown using [Marp](https://marp.app/).
It creates well-structured, visually consistent slideshows with a custom CSS theme
and exports them to HTML, PDF, or PPTX.

## Trigger Conditions

Activate this skill when the user asks to:
- Create slides, a presentation, or a slideshow
- Convert Markdown to slides
- Generate a deck or presentation file
- Use Marp to build slides

## Behavior

### 1. Gather Requirements

Before generating slides, clarify the following if not already specified:

- **Topic / content**: What should the slides cover?
- **Output format**: HTML (default), PDF, or PPTX
- **Output filename**: e.g. `slides.html` (default: same basename as the `.md` file)
- **Existing Markdown**: If the user has existing content, use it as the source

> **Theme is always the custom CSS theme** at `.claude/skills/slide-maker/theme.css`.
> Do not use Marp's built-in themes (`default`, `gaia`, `uncover`).

### 2. Install Marp CLI (if not already installed)

Check whether `@marp-team/marp-cli` is available and install it if needed:

```bash
# Check
npx @marp-team/marp-cli --version 2>/dev/null || echo "not found"

# Install globally (optional — npx works without a global install)
npm install -g @marp-team/marp-cli
```

### 3. Create the Markdown File

Write a `.md` file using the **three mandatory slide types** described below.
Always load the custom theme via the front matter.

**Mandatory front matter:**

```markdown
---
marp: true
theme: custom
paginate: true
style: |
  @import url('.claude/skills/slide-maker/theme.css');
---
```

> Alternatively, pass the theme file via CLI with
> `--theme .claude/skills/slide-maker/theme.css`.

---

## Slide Types (REQUIRED — always use all three)

### ① Cover Slide (`_class: cover`)

- Use **once** at the beginning of the deck.
- Displays the presentation title (large, centered) and author / date below it.
- Logo, page number, and CONFIDENTIAL label are **not shown**.

```markdown
---
marp: true
theme: custom
paginate: true
---

<!-- _class: cover -->

# Presentation Title

Author Name
2026-03-12
```

---

### ② Body Slides (default, no special class)

Use for all content slides. **Every body slide must include all four elements:**

| Element | Position | Description |
|---|---|---|
| Dummy LOGO | Top-right | Rectangle border containing the text "LOGO" |
| Page number | Bottom-right | Marp's built-in `paginate` feature |
| CONFIDENTIAL | Bottom-left | Font size 10 px, color #999999 |
| Summary box | Below body content | Borderless-background box (`>` blockquote) with a one-sentence summary of the slide |

**The summary box is mandatory and must never be omitted.**
Write it as a Markdown blockquote (`> ...`) at the end of the slide content.
The custom CSS renders it as a bordered, transparent box.

**Template:**

```markdown
---

## Slide Title

- Bullet point A
- Bullet point B
- Bullet point C

> One-sentence summary of this slide's key message.
```

**Rules:**
- One idea per slide — keep slides focused and uncluttered.
- Use `##` for slide titles; reserve `#` for the cover slide only.
- Limit bullet points to 3–5 items per slide.
- Add speaker notes with `<!-- ... -->` comments below slide content when helpful.
- Use fenced code blocks with language tags for syntax highlighting.
- Reference images with `![alt text](path/to/image.png)`.

---

### ③ Closing Slide (`_class: closing`)

- Use **once** at the end of the deck.
- Displays only a large LOGO box (border + "LOGO" text) centered on the slide.
- No other elements (no title, no bullets, no logo in corner, no page number, no CONFIDENTIAL).

```markdown
---

<!-- _class: closing -->

<div class="logo-box">LOGO</div>
```

---

## Color Theme (Custom CSS)

The custom theme is stored at `.claude/skills/slide-maker/theme.css`.

| Role | Value |
|---|---|
| Background | `#F2F2F2` (light gray) |
| Body text | `#333333` (charcoal gray) |
| Box border / LOGO border | `#AAAAAA` |
| CONFIDENTIAL text | `#999999`, 10 px |

Do **not** override these colors inline in the Markdown unless the user explicitly requests it.

---

## Full Slide Template

```markdown
---
marp: true
theme: custom
paginate: true
---

<!-- _class: cover -->

# Presentation Title

Author Name
2026-03-12

---

## First Topic

- Key point 1
- Key point 2
- Key point 3

> Summary: This slide covers the three key points of the first topic.

---

## Second Topic

- Detail A
- Detail B
- Detail C

> Summary: Details A through C together form the second major theme.

---

<!-- _class: closing -->

<div class="logo-box">LOGO</div>
```

---

## Generate Output

Run Marp CLI, always specifying the custom theme file:

```bash
# HTML output (default)
npx @marp-team/marp-cli slides.md \
  --theme .claude/skills/slide-maker/theme.css \
  --output slides.html

# PDF output
npx @marp-team/marp-cli slides.md \
  --theme .claude/skills/slide-maker/theme.css \
  --output slides.pdf --pdf

# PPTX output
npx @marp-team/marp-cli slides.md \
  --theme .claude/skills/slide-maker/theme.css \
  --output slides.pptx --pptx

# Watch mode (auto-rebuild on save)
npx @marp-team/marp-cli slides.md \
  --theme .claude/skills/slide-maker/theme.css \
  --watch --output slides.html
```

**Never** omit `--theme .claude/skills/slide-maker/theme.css` from the CLI command.

---

## Report Results

After generation, tell the user:
- The path to the output file
- How many slides were created (cover + body slides + closing)
- How to open or share the file
- Any warnings from the Marp CLI output

---

## Example Workflow

**User:** "Create a 5-slide presentation about climate change in PDF format."

**Steps:**
1. Create `climate-change.md` with:
   - 1 cover slide
   - 3 body slides (each with a summary blockquote)
   - 1 closing slide
2. Run:
   ```bash
   npx @marp-team/marp-cli climate-change.md \
     --theme .claude/skills/slide-maker/theme.css \
     --output climate-change.pdf --pdf
   ```
3. Report: "Generated `climate-change.pdf` with 5 slides (1 cover, 3 body, 1 closing)."

---

## Error Handling

| Error | Resolution |
|---|---|
| `marp: command not found` | Use `npx @marp-team/marp-cli` instead of `marp` |
| PDF generation fails | Try `--allow-local-files`; install Chromium or `puppeteer` |
| Images not found | Use absolute paths or place images alongside the `.md` file |
| Theme not applied | Verify path to `theme.css`; pass with `--theme` flag |
| Summary box not styled | Confirm `theme.css` is loaded and the blockquote `>` syntax is used |

## Notes

- Marp requires Node.js 18+. Verify with `node --version`.
- The custom theme file is at `.claude/skills/slide-maker/theme.css`.
  Do not delete or rename it; it is required for all slide generation.
- For advanced layouts, refer to Marp's [Marpit](https://marpit.marp.app/) directives.
