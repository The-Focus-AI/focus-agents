---
name: research
description: Research a topic on the web and generate an academic-style Markdown report with thorough source gathering
argument-hint: "<topic>"
allowed-tools:
  - WebSearch
  - WebFetch
  - Write
  - Read
  - Glob
  - AskUserQuestion
---

# Research Command

Conduct thorough web research on a topic and generate a comprehensive academic-style report.

## Process

### Step 1: Clarify Research Scope

Before starting research, ask clarifying questions to refine the scope:

1. **If the topic is broad**, ask:
   - "What specific aspect of [topic] interests you most?"
   - "Should I focus on recent developments, historical context, or both?"
   - "Any particular angle or perspective you want emphasized?"

2. **If the topic is specific enough**, confirm understanding:
   - "I'll research [topic] focusing on [inferred aspects]. Sound good?"

Use the AskUserQuestion tool to gather this input interactively.

### Step 2: Conduct Web Research

Search thoroughly using WebSearch, targeting 10+ diverse sources:

1. **Initial broad searches** to map the landscape
2. **Specific targeted searches** for depth on key aspects
3. **Search for opposing viewpoints** to ensure balanced coverage

For each promising result, use WebFetch to gather detailed content.

### Step 3: Evaluate Sources

Apply credibility criteria to each source:
- Authority: Who published this? What are their credentials?
- Currency: When was this published? Is it current enough?
- Accuracy: Can claims be verified elsewhere?
- Purpose: Is this informational or promotional?

Prioritize:
- Official documentation and primary sources
- Academic or research publications
- Established news organizations
- Expert analysis from credentialed professionals

### Step 4: Synthesize Findings

Organize information thematically:
- Identify 3-5 major themes across sources
- Note where sources agree (consensus)
- Note where sources disagree (debates)
- Extract key statistics, quotes, and insights

### Step 5: Generate Report

Create the report in `./reports/` directory.

**Choose the appropriate template from `skills/research-methodology/references/templates/`:**
- **Standard Academic Report** - `templates/academic.md` (30-60 min)
- **Executive Summary** - `templates/executive-summary.md` (15-30 min)
- **Comparative Analysis** - `templates/comparative-analysis.md` (20-40 min)
- **Literature Review** - `templates/literature-review.md` (45-90 min)
- **Quick Report** - `templates/quick-report.md` (10-15 min)
- **Technical Implementation** - `templates/technical-implementation.md` (30-45 min)

See `skills/research-methodology/references/template-guide.md` for selection guidance.

Use the Skill tool to invoke `Research Methodology` if you need detailed guidance on report structure and source evaluation.

### Step 6: Save and Report

1. Create the `./reports/` directory if it doesn't exist
2. Save the report as `./reports/YYYY-MM-DD-topic-slug.md`
3. Summarize what was found and where the report was saved

## File Naming

Use date prefix with kebab-case topic:
- "AI trends" → `2024-03-15-ai-trends.md`
- "renewable energy analysis" → `2024-03-15-renewable-energy-analysis.md`
- "quantum computing basics" → `2024-03-15-quantum-computing-basics.md`

## Quality Standards

Ensure the report meets these criteria:
- [ ] 10+ sources consulted
- [ ] Diverse source types (not all from one site)
- [ ] All claims properly cited with URLs
- [ ] Multiple perspectives represented
- [ ] Clear thematic organization
- [ ] Complete reference list

## Tips

- **Be thorough**: Don't stop at 3-4 sources. Dig deeper.
- **Verify claims**: Cross-reference important findings across sources
- **Note limitations**: Be transparent about what couldn't be determined
- **Include quotes**: Direct quotes with attribution add credibility
- **Stay balanced**: Present multiple perspectives on contested topics
