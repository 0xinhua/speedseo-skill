# speedseo-skill

## Purpose

A blog research and writing skill for SEO and GEO. Research keywords and search results, verify facts, write articles, and integrate them into a website as needed. Drafts are delivered for human review and are not published automatically.

## Requirements

- An AI assistant that can read local files and follow skill instructions.
- The DataForSEO plugin / MCP, or an API Login and API Password. See the [DataForSEO guide](references/dataforseo.md) for setup instructions.
- Web search and page reading capabilities for research and fact verification.

## Usage

Invoke this skill, then ask the assistant:

```text
Write an article for [website] targeting [keyword].
```

## Skill Structure

```text
speedseo-skill/
├── README.md                       Overview and usage
├── SKILL.md                        Required rules and research, writing, and website integration workflows
└── references/
    ├── dataforseo.md               DataForSEO setup and usage
    ├── research-record.md          Research record template
    └── structured-data.md          Structured data rules
```
