---
name: cidr-document-format
description: "Use this skill whenever the user asks to create any document, report, memo, policy, SOP, proposal, playbook, or formatted deliverable for CIDR (Caller ID Reputation). This skill ensures every document uses the official CIDR cover page layout, color palette, heading hierarchy, and professional formatting. Trigger on any request involving document creation, Word docs, policies, procedures, guides, or any written deliverable that should look polished and consistent with the CIDR brand. Even if the user doesn't explicitly mention formatting, use this skill for any CIDR document output."
version: 1.0.0
---

# CIDR Document Formatting Standard

Every document created for Caller ID Reputation (CIDR) MUST follow this formatting specification exactly. This ensures brand consistency across all SOPs, policies, proposals, and deliverables.

**Before writing any code**, also read the core docx skill at `/mnt/skills/public/docx/SKILL.md` for the `docx-js` API reference and validation steps.

## Color Palette

These are the ONLY colors to use in CIDR documents:

| Token              | Hex       | Usage                                                    |
|--------------------|-----------|----------------------------------------------------------|
| `NAVY_DARK`        | `1F3864`  | Company name "CALLER ID REPUTATION", H1 headings         |
| `BLUE_ACCENT`      | `2E75B6`  | Document title, horizontal rules, H2 headings, links     |
| `GRAY_SUBTITLE`    | `595959`  | Cover page subtitle, metadata lines                      |
| `BODY_TEXT`        | `333333`  | All body paragraph text                                  |
| `GRAY_LIGHT`      | `808080`  | Page header text, footer text                            |
| `RULE_COLOR`       | `2E75B6`  | Horizontal divider lines (cover page + under H1s)        |
| `CALLOUT_BG`       | `F2F2F2`  | Callout/highlight box background fill                    |
| `CALLOUT_BORDER`   | `2E75B6`  | Left border on callout boxes                             |
| `TABLE_HEADER_BG`  | `1F3864`  | Table header row background                              |
| `TABLE_HEADER_TEXT` | `FFFFFF`  | Table header row text                                    |
| `TABLE_ALT_ROW`    | `F2F7FB`  | Alternating table row fill                               |

## Font Stack

| Element           | Font          | Size (pt) | Weight   | Color         |
|-------------------|---------------|-----------|----------|---------------|
| Company name      | Calibri       | 26        | Bold     | `NAVY_DARK`   |
| "CIDR" acronym    | Calibri       | 16        | Normal   | `BLUE_ACCENT` |
| Document title    | Calibri       | 20        | Bold     | `NAVY_DARK`   |
| Cover subtitle    | Calibri       | 11        | Normal   | `GRAY_SUBTITLE` |
| Cover metadata    | Calibri       | 11        | Normal   | `GRAY_SUBTITLE` |
| H1 (numbered)     | Calibri       | 18        | Bold     | `NAVY_DARK`   |
| H2 (numbered)     | Calibri       | 14        | Bold     | `BLUE_ACCENT` |
| H3                | Calibri       | 12        | Bold     | `NAVY_DARK`   |
| Body text         | Calibri       | 11        | Normal   | `BODY_TEXT`   |
| Bold body         | Calibri       | 11        | Bold     | `BODY_TEXT`   |
| Callout title     | Calibri       | 11        | Bold     | `BODY_TEXT`   |
| Footer text       | Calibri       | 9         | Normal   | `GRAY_LIGHT`  |
| Page header       | Calibri       | 9         | Italic   | `GRAY_LIGHT`  |

## Page Setup

- Paper: US Letter (12240 × 15840 DXA)
- Margins: 1 inch all sides (1440 DXA)
- Content width: 9360 DXA

## Cover Page Layout (Section 1 — No Header/Footer)

The cover page is its own section with no header or footer. It contains these elements in order, all **center-aligned**:

1. **Vertical spacing** — approximately 2 inches (2880 DXA) of space before the company name to push content to the upper-middle of the page.

2. **"CALLER ID REPUTATION"** — 26pt Calibri Bold, `NAVY_DARK`, center-aligned, all caps.

3. **"CIDR"** — 16pt Calibri, `BLUE_ACCENT`, center-aligned. Small spacing after (200 DXA).

4. **Horizontal rule** — A full-width paragraph with a top border: `BLUE_ACCENT`, 1pt, `BorderStyle.SINGLE`. Spacing before: 400 DXA.

5. **Document Title** — 20pt Calibri Bold, `NAVY_DARK`, center-aligned. This is the actual title of the document (e.g., "Trade Show & Conference Conduct Policy"). It sits between the two horizontal rules.

6. **Horizontal rule** — Same as #4, but using a bottom border on the title paragraph or a top border on the next paragraph.

7. **Subtitle line** — 11pt Calibri, `GRAY_SUBTITLE`, center-aligned. Format: `Standard Operating Procedure  |  [Document Type]` (e.g., "Rules of Engagement", "Sales Playbook", "Revenue Operations"). Spacing before: 300 DXA.

8. **Metadata block** — 11pt Calibri, `GRAY_SUBTITLE`, center-aligned, each on its own line. Spacing before the block: 400 DXA. Lines:
   - `Department: [Department Name]`
   - `Effective Date: [Full date, e.g., February 19th, 2026]`
   - `Version: [X.X]`
   - `Approved By: Shawn Stiffler, CRO`

**IMPORTANT**: The cover page section must specify `sectionType: SectionType.NEXT_PAGE` or equivalent so the body content starts on a new page.

## Body Pages Layout (Section 2+)

### Page Header (Right-Aligned)
- Text: `CIDR  |  [Short Document Title]` — 9pt Calibri Italic, `GRAY_LIGHT`, right-aligned.
- Only appears on body pages (not the cover page).

### Page Footer
- A thin horizontal rule (`GRAY_LIGHT`, 0.5pt) spanning the content width.
- Below the rule: `Confidential – Caller ID Reputation (CIDR)` left-aligned, and `Page [X]` right-aligned. Both 9pt Calibri, `GRAY_LIGHT`.
- Use tab stops (not a table) for the two-column footer layout per the docx skill guidance.

### Heading Hierarchy

**H1 — Major Sections** (numbered: "1.", "2.", "3.", etc.)
- 18pt Calibri Bold, `NAVY_DARK`
- Numbered manually in the text (e.g., "1. Purpose & Scope")
- Bottom border: `BLUE_ACCENT`, 1pt, full width — applied as a paragraph border
- Spacing: 480 DXA before, 240 DXA after

**H2 — Subsections** (numbered: "2.1", "2.2", etc.)
- 14pt Calibri Bold, `BLUE_ACCENT`
- Spacing: 360 DXA before, 180 DXA after

**H3 — Sub-subsections** (no number, bold label)
- 12pt Calibri Bold, `NAVY_DARK`
- Spacing: 240 DXA before, 120 DXA after

### Body Text
- 11pt Calibri, `BODY_TEXT`
- Line spacing: 1.15 (276 DXA line rule)
- Paragraph spacing: 120 DXA after each paragraph
- Justified alignment

### Bullet Lists
- Use `LevelFormat.BULLET` (never unicode bullets)
- 11pt Calibri, `BODY_TEXT`
- Indent: 720 DXA left, 360 DXA hanging
- Spacing: 60 DXA after each item

### Callout / Highlight Boxes
Used for "Key Principle", "Important", "Zero-Tolerance" blocks, etc.
- Implemented as a table with a single cell
- Left border: 3pt solid `CALLOUT_BORDER` (BLUE_ACCENT)
- Cell fill: `CALLOUT_BG` (F2F2F2)
- Cell margins: 120 DXA all sides
- Title line: 11pt Calibri Bold, `BODY_TEXT`
- Body: 11pt Calibri, `BODY_TEXT`

### Tables
- Header row: `TABLE_HEADER_BG` background, `TABLE_HEADER_TEXT` text, 11pt Calibri Bold
- Alternating rows: white and `TABLE_ALT_ROW`
- Cell borders: 0.5pt `BFBFBF`
- Cell padding: 80 DXA top/bottom, 120 DXA left/right
- Always use `WidthType.DXA` and set both `columnWidths` and cell `width`

### Violation / Severity Tables
For policy documents with violation frameworks:
- 3-column layout: Violation Type | Examples | Consequence
- Use the standard table formatting above
- Bold the violation severity level in column 1

## Section Numbering Convention

All major sections are manually numbered starting at 1. Subsections use decimal notation (1.1, 1.2, 2.1, etc.). Do NOT use Word's automatic numbering for section headers — manually prefix the number in the heading text.

## Document Footer Confidentiality

Every page footer must include: `Confidential – Caller ID Reputation (CIDR)`

## Implementation Checklist

When creating a CIDR document, verify:
1. Cover page uses exact layout with all elements in the correct order
2. Color palette matches — no other colors used
3. Font is Calibri throughout (never Arial, Times, etc.)
4. H1 headings have the blue underline rule
5. Page headers and footers are present on body pages only
6. Footer includes confidentiality notice and page number
7. Tables use the header/alternating-row pattern
8. Callout boxes use left-border + light gray fill pattern
9. All body text is justified
10. Document validated with `python scripts/office/validate.py`
