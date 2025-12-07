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

Conduct thorough web research on a topic and generate a comprehensive report using the appropriate template.

## Process

### Step 1: Clarify Research Scope AND Select Template

Before starting research, you MUST:

1. **Clarify scope** (if topic is broad):
   - "What specific aspect of [topic] interests you most?"
   - "Should I focus on recent developments, historical context, or both?"

2. **Select report template** - Use AskUserQuestion to ask:
   - Question: "What type of report do you need?"
   - Options:
     - **Full technical guide** - For library/tool selection, implementation guidance with code examples
     - **Comparative analysis** - For evaluating options, pros/cons, decision matrices
     - **Standard academic** - For comprehensive topic analysis, knowledge base articles
     - **Executive summary** - For quick business decisions, stakeholder briefings
     - **Quick report** - For rapid answers, preliminary research
     - **Literature review** - For academic surveys, state-of-the-art analysis

3. **Map selection to template file:**

   | User Selection | Template File |
   |----------------|---------------|
   | Full technical guide | `technical-implementation.md` |
   | Comparative analysis | `comparative-analysis.md` |
   | Standard academic | `academic.md` |
   | Executive summary | `executive-summary.md` |
   | Quick report | `quick-report.md` |
   | Literature review | `literature-review.md` |

### Step 2: Read the Template (MANDATORY)

**CRITICAL: You MUST read the selected template before conducting research.**

1. Use the Read tool to read the template from:
   `${CLAUDE_PLUGIN_ROOT}/skills/research-methodology/references/templates/[selected-template].md`

2. Note the required sections, YAML frontmatter structure, and formatting patterns.

3. The template structure will guide what information you need to gather during research.

### Step 3: Conduct Web Research

Search thoroughly using WebSearch, targeting 10+ diverse sources:

1. **Initial broad searches** to map the landscape
2. **Specific targeted searches** for depth on key aspects
3. **Search for opposing viewpoints** to ensure balanced coverage

For each promising result, use WebFetch to gather detailed content.

**For Technical Implementation reports**, specifically search for:
- Official documentation
- GitHub repositories (stars, recent activity)
- Comparison articles
- Known issues or limitations
- Alternative libraries/tools

### Step 4: Evaluate Sources

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

### Step 5: Synthesize Findings

Organize information thematically:
- Identify 3-5 major themes across sources
- Note where sources agree (consensus)
- Note where sources disagree (debates)
- Extract key statistics, quotes, and insights

### Step 6: Generate Report Using Template (MANDATORY)

**You MUST follow the template structure exactly.**

1. Create the `./reports/` directory if it doesn't exist

2. Write the report following the template you read in Step 2:
   - Include ALL sections from the template
   - Use the YAML frontmatter format if the template specifies one
   - Follow the exact heading structure
   - Include all required subsections (e.g., "Anti-Patterns & Pitfalls" for technical reports)

3. Use numbered references `[1]`, `[2]`, etc. and include full reference list at the end

4. Save as `./reports/YYYY-MM-DD-topic-slug.md`

### Step 7: Verify Template Compliance

Before finishing, verify your report includes:

**For Technical Implementation:**
- [ ] YAML frontmatter with `use_when`, `avoid_when`, `project_context`
- [ ] Summary with metrics (GitHub stars, downloads, etc.)
- [ ] Philosophy & Mental Model section
- [ ] Setup section with code examples
- [ ] 3-5 Core Usage Patterns with code
- [ ] Anti-Patterns & Pitfalls with bad/good examples
- [ ] Decision Criteria table with weights
- [ ] Alternatives Considered with "choose this instead when"
- [ ] Caveats & Limitations
- [ ] Numbered References with descriptions

**For Comparative Analysis:**
- [ ] Comparison matrix/table
- [ ] Per-option analysis
- [ ] Recommendation with rationale

**For all reports:**
- [ ] 10+ sources consulted
- [ ] All claims properly cited
- [ ] Complete reference list with URLs

## File Naming

Use date prefix with kebab-case topic:
- "AI trends" → `2024-03-15-ai-trends.md`
- "atproto bookmark app" → `2024-03-15-atproto-bookmark-app.md`

## Tips

- **Read the template first** - It tells you what to research
- **Be thorough**: Don't stop at 3-4 sources. Dig deeper.
- **Verify claims**: Cross-reference important findings across sources
- **Note limitations**: Be transparent about what couldn't be determined
- **Include quotes**: Direct quotes with attribution add credibility
- **Stay balanced**: Present multiple perspectives on contested topics
