# CIDR Document Format Plugin

A Claude Code plugin that ensures all Caller ID Reputation (CIDR) documents follow the official brand formatting standard.

## What It Does

This plugin automatically triggers whenever you create any document, report, memo, policy, SOP, proposal, playbook, or formatted deliverable for CIDR. It enforces:

- Official CIDR cover page layout
- Brand color palette (navy, blue accent, grays)
- Calibri font stack with correct sizes and weights
- Heading hierarchy with numbered sections
- Styled tables, callout boxes, and bullet lists
- Confidential footer on every page

## Structure

```
cidr-document-plugin/
├── README.md
└── skills/
    └── cidr-document-format/
        └── SKILL.md
```

## Installation

Clone this repo and register it as a Claude Code plugin:

```bash
git clone <your-repo-url> ~/Documents/cidr-document-plugin
```

Then in Claude Code, add the plugin path to your configuration.

## Usage

The skill activates automatically when you ask Claude Code to create any CIDR document. No slash command needed — just describe the document you want and the formatting will be applied.
