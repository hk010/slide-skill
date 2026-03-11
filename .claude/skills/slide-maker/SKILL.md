# Skill: Marp Slide Maker

## Overview

This skill generates presentation slides from Markdown using [Marp](https://marp.app/).
It creates well-structured, visually appealing slideshows and exports them to HTML, PDF, or PPTX.

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
- **Theme**: `default`, `gaia`, or `uncover` (default: `default`)
- **Output filename**: e.g. `slides.html` (default: same basename as the `.md` file)
- **Existing Markdown**: If the user has existing content, use it as the source

### 2. Install Marp CLI (if not already installed)

Check whether `@marp-team/marp-cli` is available and install it if needed:

```bash
# Check
npx @marp-team/marp-cli --version 2>/dev/null || echo "not found"

# Install globally (optional — npx works without a global install)
npm install -g @marp-team/marp-cli
```

### 3. Create the Markdown File

Write a `.md` file with a valid Marp front matter block and slide separators (`---`).

**Template:**

```markdown
---
marp: true
theme: default
paginate: true
---

# Title Slide

Subtitle or author name

---

## Slide 2: Key Point

- Bullet point A
- Bullet point B
- Bullet point C

---

## Slide 3: Another Section

Content goes here.

---

## Summary

- Point 1
- Point 2
- Point 3
```

**Front matter options:**

| Key | Values | Description |
|---|---|---|
| `marp` | `true` | Required — enables Marp processing |
| `theme` | `default` / `gaia` / `uncover` | Visual theme |
| `paginate` | `true` / `false` | Show page numbers |
| `backgroundColor` | CSS color | Slide background color |
| `color` | CSS color | Text color |
| `size` | `16:9` / `4:3` | Aspect ratio |

Per-slide directives (placed at the top of a slide, after `---`):

```markdown
---
<!-- _class: lead -->
<!-- _backgroundColor: #1e3a5f -->
<!-- _color: white -->

# Hero Slide
```

### 4. Generate the Output

Run Marp CLI to produce the output file:

```bash
# HTML output (default)
npx @marp-team/marp-cli slides.md --output slides.html

# PDF output
npx @marp-team/marp-cli slides.md --output slides.pdf --pdf

# PPTX output
npx @marp-team/marp-cli slides.md --output slides.pptx --pptx

# Specify a theme
npx @marp-team/marp-cli slides.md --theme gaia --output slides.html

# Watch mode (auto-rebuild on save)
npx @marp-team/marp-cli slides.md --watch --output slides.html
```

### 5. Report Results

After generation, tell the user:
- The path to the output file
- How many slides were created
- How to open or share the file
- Any warnings from the Marp CLI output

## Example Workflow

**User:** "Create a 5-slide presentation about climate change in PDF format."

**Steps:**
1. Create `climate-change.md` with Marp front matter and 5 slides covering the topic
2. Run `npx @marp-team/marp-cli climate-change.md --output climate-change.pdf --pdf`
3. Report: "Generated `climate-change.pdf` with 5 slides."

## Slide Writing Guidelines

- **One idea per slide** — keep slides focused and uncluttered
- **Use headings** (`##`) for slide titles; use `#` only on the title slide
- **Limit bullet points** — 3–5 items per slide maximum
- **Add speaker notes** with `<!-- ... -->` comments below slide content when helpful
- **Use code blocks** with language tags for syntax highlighting
- **Images**: reference local files or URLs — `![alt text](path/to/image.png)`
- **Separate slides** with `---` on its own line

## Error Handling

| Error | Resolution |
|---|---|
| `marp: command not found` | Run with `npx @marp-team/marp-cli` instead of `marp` |
| PDF generation fails | Install Chromium: `npx @marp-team/marp-cli --allow-local-files` or install `puppeteer` |
| Images not found | Use absolute paths or ensure images are in the same directory as the `.md` file |
| Theme not applied | Confirm the theme name is one of `default`, `gaia`, `uncover` |

## Notes

- Marp requires Node.js 18+. Verify with `node --version`.
- For custom CSS themes, create a `.css` file and reference it with `--theme path/to/theme.css`.
- For advanced layouts, use Marp's [Marpit](https://marpit.marp.app/) directives.
