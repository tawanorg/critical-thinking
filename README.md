# Critical Developer Mindset

A Claude Code skill that embodies the senior developer mindset: **trust no one's requirements blindly, see what others don't see, and apply engineering knowledge beyond the acceptance criteria.**

## Philosophy

> "AC is scope, not specification. Your engineering brain defines how to do it right."

This skill transforms how you approach any technical task by applying a systematic 7-step critical analysis framework combined with powerful research and code analysis tools.

## The 7-Step Framework

```
1. QUESTION   → What gaps exist in the requirement?
2. RESEARCH   → What don't I know? (Use tools to find out)
3. VALIDATE   → Is this the actual problem to solve?
4. EXPAND     → What ripple effects will this cause?
5. SECURE     → What security/reliability concerns exist?
6. FUTURE     → Will this scale appropriately?
7. IMPLEMENT  → With all insights applied
```

## Features

### Critical Thinking
- Gap detection (edge cases, concurrency, state, failures, dependencies)
- Rationalization rejection (excuses developers make)
- Red flags identification
- Stakeholder communication templates

### Research Capabilities
- Web research (Firecrawl, WebSearch, WebFetch)
- GitHub research (code search, issue search, file contents)
- Documentation parsing (PDFs, Word, Excel)

### Code Analysis (LSP)
- Project-wide diagnostics
- Symbol navigation and references
- Type information and documentation

### Structural Code Search (AST)
- Pattern-based code search
- Safe refactoring across files

### Complex Reasoning
- Sequential thinking with revision capability
- Python REPL for calculations and analysis

### Memory & Context
- Project memory persistence
- Session search for historical context
- Knowledge graph storage

## Installation

### For Claude Code

Copy the skill to your skills directory:

```bash
# Clone the repo
git clone git@github.com:tawanorg/critical-thinking.git

# Symlink to Claude Code skills
ln -s $(pwd)/critical-thinking ~/.claude/skills/critical-developer-mindset
```

Or copy directly:

```bash
cp -r critical-thinking ~/.claude/skills/critical-developer-mindset
```

### For Other Runtimes

The skill follows the [agentskills.io specification](https://agentskills.io/specification) and can be adapted for:
- Codex CLI
- Copilot CLI
- Gemini CLI

## Usage

### Invoke the Skill

```
/critical-developer-mindset
```

### Use the Requirement Analyst Agent

```bash
# Via OMC Team
/team requirement-analyst "Analyze: Users should be able to export their data as CSV"

# Via Task Tool
Use Task tool with subagent_type: "oh-my-claudecode:architect"
```

## The Critical Developer Creed

```
┌─────────────────────────────────────────────────────────────┐
│                 THE CRITICAL DEVELOPER CREED                │
├─────────────────────────────────────────────────────────────┤
│ 1. AC is scope, not specification                          │
│ 2. Question everything, assume nothing                      │
│ 3. Research before assuming - verify with official sources  │
│ 4. Think about failure before success                       │
│ 5. Security is implicit, never optional                     │
│ 6. Your code, your responsibility                           │
│ 7. See what others don't see                                │
│ 8. Speak up when something's wrong                          │
└─────────────────────────────────────────────────────────────┘
```

## Files

- `SKILL.md` - Main skill definition with the 7-step framework
- `AGENTS.md` - Agent configurations for automated analysis
- `README.md` - This file

## Requirements

For full functionality, ensure these MCP servers are configured:
- `firecrawl` - Web search and scraping
- `github` - GitHub API access
- `memory` - Knowledge graph
- `oh-my-claudecode` - LSP, AST, Python REPL, project memory

## License

MIT

## Author

Created with Claude Code.
