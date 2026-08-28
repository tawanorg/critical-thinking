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
- Version-correct library docs (Context7)
- General web research (WebSearch, WebFetch)
- GitHub research through the `gh` CLI

### Code Analysis (Serena)
- Symbol navigation: definitions, references, implementations
- Language-server diagnostics per file or per symbol
- Symbol-level edits and project-wide rename

### Memory & Context (Serena)
- Project memories that survive between sessions

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
# Delegate the analysis to a subagent
Use the Agent tool with subagent_type "general-purpose" and a prompt of
"Apply the critical-developer-mindset skill to: Users should be able to
export their data as CSV"
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

Two MCP servers, both optional — the framework works without them, but the
tool tables in `SKILL.md` assume they are present:

| Server | Provides | Install |
|---|---|---|
| [serena](https://github.com/oraios/serena) | Symbol-level code navigation and editing over a real language server | `uv tool install serena-agent`, then `claude mcp add serena -s user -- serena start-mcp-server --context ide-assistant` |
| [context7](https://github.com/upstash/context7) | Version-correct library documentation | `claude mcp add context7 -s user --transport http https://mcp.context7.com/mcp` |

GitHub research goes through the `gh` CLI rather than an MCP server. Google
Workspace tools come from the connectors on your Claude account, not from
anything installed here.

## License

MIT

## Author

Created with Claude Code.
