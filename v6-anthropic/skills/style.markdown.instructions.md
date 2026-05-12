---
description: "Markdown style guide"
applyTo: "**/*.md"
---

<markdown_style>

# Markdown Style Guide

## Introduction

This consolidated Markdown style guide combines our existing rules with widely-used best practices and examples from the Markdown reference material. It covers basic syntax, extended features, compatibility notes, and a few safe "hacks" when HTML support is available.

Use this guide when authoring documentation, READMEs, and other Markdown content in the repository. When in doubt, prefer CommonMark/GitHub Flavored Markdown (GFM) compatible constructs for the best cross-tool behavior.

## Headings

Use ATX-style headings (hash marks) and put a single space after the hashes. Start documents with # for the main title and do not skip levels (e.g., don't jump from ## to ####). Add a blank line before and after headings for better compatibility with Markdown processors.

Rules:

* Use one space after # (e.g., ## Section title).
* Use sentence case for headings.
* Keep heading depth meaningful and avoid skipping levels.

Good:

# Project Phoenix

## Overview

### Requirements

Avoid:

-#MissingSpace

## Paragraphs and Line Breaks

Paragraphs are separated by one blank line. Avoid indenting normal paragraphs with spaces or tabs (unless intentionally creating a code block).

To create a line break (soft break), prefer an explicit <br> tag or use two trailing spaces at the end of a line for compatibility; note that trailing spaces are easy to miss in source.

Rules:

* Use a blank line to separate paragraphs.
* Avoid leading spaces/tabs on paragraph lines.
* For visible new lines inside a paragraph: use two trailing spaces + Enter or <br> when supported.

## Emphasis (Bold, Italic)

Prefer asterisks for intra-word emphasis to avoid processor differences with underscores.

Rules:

* Italic: *text*
* Bold: **text**
* Bold + Italic: ***text***

Do not rely on underscores for mid-word emphasis (e.g., use Love**is**bold not Love__is__bold).

## Lists

Use hyphens (-) for unordered lists for consistency. For ordered lists use 1. (the renderer will number list items correctly). Indent nested list content with four spaces.

Rules:

* Unordered lists: - item
* Ordered lists: 1. item
* Indent nested lists with 4 spaces.
* Don't mix list delimiters within the same list.

To keep lists readable, put a blank line before the list and between list blocks when appropriate.

## Links and Images

Use inline link syntax: [text](https://example.com) and provide descriptive link text. For images use the same pattern prefixed with ! and always include alt text.

Rules:

* Links: [label](https://example.com)
* Images: ![alt text](path/to/image.png)
* Avoid click here as link text; be descriptive instead.

If you need links to open in a new tab or to add attributes, use HTML anchors when supported (e.g., <a href="..." target="_blank">).

## Code

Inline code: use single backticks: `code`. Use fenced code blocks (three backticks) for longer snippets. Specify the language for syntax highlighting when supported (e.g., json or python).

Rules:

* Inline: `variable`
* Block:```
def fn():

return True
```

- Add a language after the opening fence for highlighting: ```python

When you need backticks inside a fenced code block, you can fence with a larger number of backticks.

## Blockquotes

Use > to create blockquotes. Put blank lines before and after blockquotes for better compatibility. Blockquotes can contain headings, lists, and other block elements, but remember not every processor supports every combination.

## Horizontal Rules

Use three or more hyphens (---) for a visual section break.

## Extended Syntax (Tables, Footnotes, IDs, etc.)

Note: Extended features vary by processor. Prefer CommonMark/GFM-compatible constructs and check your target renderer.

Tables:

- Use pipes (|) and hyphens (---) to build tables. Add pipes at the ends of rows for readability.
- Align columns with colons in header separators: :---, :---:, ---:.
- Avoid complex block-level content inside table cells; if needed, use HTML.

Example:

```markdown
| Name | Role |
| --- | --- |
| Alice | Developer |
```

Fenced code blocks and syntax highlighting:

- Use triple backticks and specify a language for highlighting (```json, ```bash, etc.).

Footnotes:

- Use footnote references like [^1] and define them [^1]: note text anywhere in the document (not inside lists/tables). Footnotes are numbered in output.

Heading IDs and anchor links:

- Many processors support {#custom-id} after a heading. Use these for internal linking and ToC generation.

Definition lists, strikethrough, task lists, emoji, highlights, subscript, superscript:

- These are supported in various extended syntaxes (GFM/MultiMarkdown). Use them when your renderer supports them:
- Definition lists: Term\n: Definition
- Strikethrough: ~~text~~
- Task lists: - [ ] and - [x]
- Emoji shortcodes: :joy: (renderer-dependent)
- Highlight: ==text== (not widely supported)
- Subscript: H~2~ (renderer-dependent)
- Superscript: X^2^ (renderer-dependent)

## Automatic URL Linking

Many renderers auto-link bare URLs (e.g., http://example.com). To prevent linking, mark a URL as code: `http://example.com`.

## Hacks and HTML Fallbacks (Use Sparingly)

If your Markdown processor allows raw HTML, some layout or styling needs can be solved with HTML. Use these hacks only when necessary and document the dependency on HTML support.

Common fallbacks:

- Centering: <p style="text-align:center">Text</p> or deprecated <center> tag.
- Color: <span style="color:blue">text</span> (avoid unless necessary).
- Image sizing / captions: use <img width="200" height="100" src="..."> or <figure><figcaption> when supported.
- Comments (hidden in output): [comment]: # (hidden note) or [This is a comment]: # (processor-dependent but widely used).
- Table cell line breaks and lists: use <br> or HTML lists inside table cells.

Warning: HTML tags like <font> and <center> are deprecated; prefer CSS when available.

## Accessibility and Best Practices

- Always provide alt text for images.
- Use meaningful link text for screen reader users.
- Keep tables simple and avoid using them for layout.
- For long documents, consider adding a Table of Contents with heading links.

## Quick Cheat Sheet (Common patterns)

- Heading: # H1 / ## H2
- Bold / Italic: **bold** / *italic* / ***bold italic***
- Code inline: `code`
- Code block: ```python\nprint()\n```
- Link: [label](https://example.com)
- Image: ![alt](image.png)
- Table: | col | col |\n| --- | --- |\n| a | b |
- Task list: - [ ] todo / - [x] done
- Strikethrough: ~~no longer~~

## Notes on Compatibility

When in doubt follow CommonMark/GFM (GitHub Flavored Markdown) conventions. Always test documents in the target renderer (GitHub, MkDocs, VS Code preview, etc.) before publishing.

## References

- CommonMark: https://commonmark.org
- GitHub Flavored Markdown: https://github.github.com/gfm/
- The Markdown Guide: https://www.markdownguide.org

</markdown_style>