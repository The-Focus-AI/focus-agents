# tech-researcher

A Claude Code plugin for researching topics on the web and generating comprehensive academic-style Markdown reports.

## Features

- **Thorough Research**: Gathers information from 10+ sources
- **Interactive Flow**: Asks clarifying questions to refine research scope
- **Academic Reports**: Generates structured reports with abstract, findings, conclusion, and references
- **Source Persistence**: Saves research to `./reports/` folder with date-prefixed filenames
- **Proactive Activation**: Triggers automatically on research-related requests

## Usage

### Command

```
/research <topic>
```

Starts an interactive research session. The plugin will:
1. Ask clarifying questions about scope and focus
2. Search the web for relevant sources
3. Gather and synthesize information
4. Generate an academic-style Markdown report
5. Save to `./reports/YYYY-MM-DD-topic-name.md`

### Natural Language

The web-researcher agent also triggers on natural requests like:
- "Research the latest trends in AI"
- "Find information about quantum computing"
- "What's the current state of renewable energy?"

## Output Format

Reports follow an academic structure:

1. **Abstract** - Brief summary of findings
2. **Introduction** - Context and research scope
3. **Findings** - Organized by theme/topic
4. **Conclusion** - Key takeaways
5. **References** - All sources with links

## Installation

### Via Focus Marketplace (Recommended)

```bash
# Add the Focus marketplace (if not already added)
/plugin marketplace add The-Focus-AI/claude-marketplace

# Install the plugin
/plugin install focus-agents@focus-marketplace
```

Then restart Claude Code.

### Manual Installation

```bash
claude --plugin-dir /path/to/focus-agents
```

Or copy to your project's `.claude-plugin/` directory.
