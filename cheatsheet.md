---
title: "Markdown & BonBon Front Matter Cheat Sheet"
author: "Samuel S. Thorp"
pubDate: "Thu, 19 Nov 2026 08:31:00 GMT"
description: "Quick reference for Markdown syntax, BonBon YAML front matter keys, and publishing to md.thorp.uk."
urlParent: "index.md"
---

# {{page.title}}

By {{page.author}} — updated {{page.pubDate}}.

A quick reference for drafting new posts, wiring up BonBon/mdweb navigation keys, and publishing to [md.thorp.uk](index.md).

## 1. Copy-Paste New Post Template

Every file must start with `---` on line 1 (no blank lines above it) and close with `---` before your body text.

```markdown
---
title: "Post Title"
author: "Samuel S. Thorp"
pubDate: "Thu, 19 Nov 2026 08:30:00 GMT"
description: "One-sentence summary of the post."
tags: ["poetry", "faith"]
urlParent: "index.md"
urlPrev: "previous-post.md"
urlNext: "next-post.md"
---

# {{page.title}}

By {{page.author}} on {{page.pubDate}}.

Opening paragraph goes here. Keep each paragraph as one continuous line with Soft Wrap enabled, and leave a blank line between paragraphs.

## Section Heading

- Bullet item one
- Bullet item two with a [relative link](other-post.md)

> Blockquote for an excerpt or sign-off.
```

---

## 2. BonBon / Markdown Web Front Matter Keys

Markdown browsers parse these fields to wire up browser chrome buttons, tab titles, and template variables (unknown keys are safely ignored).

| Field | Purpose | Example |
| :--- | :--- | :--- |
| `title` | Page title (used in browser tab and `{{page.title}}`) | `"Notes on Scansion"` |
| `author` | Author name (used in `{{page.author}}`) | `"Samuel S. Thorp"` |
| `pubDate` | RFC 822 / GMT timestamp (used in `{{page.pubDate}}`) | `"Thu, 19 Nov 2026 08:30:00 GMT"` |
| `description` | Short summary for previews and feeds | `"Thoughts on nine-syllable lines."` |
| `urlParent` | Links the browser's **Up / Parent** navigation arrow | `"index.md"` |
| `urlPrev` | Links the browser's **Previous** navigation arrow | `"helloworld.md"` |
| `urlNext` | Links the browser's **Next** navigation arrow | `"second-post.md"` |
| `urlFirstChild` | Used on `index.md` to point **Next** to your first post | `"helloworld.md"` |
| `metaImage` | Optional preview image URL | `"https://md.thorp.uk/img/cover.png"` |
| `rightMarginImage` | Optional margin illustration supported by BonBon | `"https://md.thorp.uk/img/icon.png"` |

*Tip: Always wrap YAML values in double quotes if they contain a colon followed by a space—such as `"Part 1: Introduction"`—otherwise YAML treats the colon as a nested field.*

---

## 3. Essential Markdown Formatting Syntax

- **Headings:** `# Title` (H1), `## Section` (H2), `### Subsection` (H3) — always put a space after `#`
- **Emphasis:** `**bold text**` and `*italic text*`
- **Internal Site Links:** `[Link Text](filename.md)` or `[Older Post](2026/11/post.md)` — always include the `.md` extension so Markdown browsers stay inside reader mode rather than opening a standard web tab
- **External Web Links:** `[Main Website](https://samuelsthorp.co.uk)`
- **Images:** `![Alt text description](https://example.com/image.png)`
- **Lists:** Start lines with `- ` for bullet lists or `1. ` for numbered lists (indent sub-bullets with two spaces)
- **Blockquotes:** Start lines with `> `
- **Inline Code / Filenames:** Wrap text in single backticks like `` `index.md` ``
- **Horizontal Rule:** Three hyphens `---` on its own line (with a blank line above and below)

---

## 4. Publishing Checklist for `md.thorp.uk`

1. **Filename:** Use lowercase letters, numbers, and hyphens only (e.g., `on-writing.md`), with no spaces.
2. **Navigation Links:** Set `urlParent: "index.md"` and point `urlPrev` to your previous post (and update the previous post's `urlNext` to point to the new file).
3. **Update `index.md`:** Add a bullet link `- [Post Title](new-file.md) — Brief note.` under your Posts list so readers starting at `https://md.thorp.uk/index.md` can find it.

---

Back to [Home](index.md).
