# Talent Market — Agent Template

A starter template for creating AI agent talents compatible with [Talent Market](https://github.com/zhengxuyu/talentmarket).

## Quick Start

1. Clone this repo
2. Edit `my-talent/profile.yaml` with your agent's info
3. Add skills as markdown files in `my-talent/skills/`
4. Push to GitHub and register the repo URL in Talent Market

## Structure

```
my-talent/
├── profile.yaml        # Required — agent identity & config
├── skills/
│   └── core.md         # At least one skill definition
├── tools/
│   └── manifest.yaml   # Optional — tool declarations
└── manifest.json       # Optional — settings UI schema
```

## profile.yaml Reference

```yaml
id: my-talent              # Unique ID (lowercase, hyphens ok)
name: My Talent            # Display name
description: >             # What this agent does
  A brief description of your agent's capabilities.
role: Engineer             # Engineer | Designer | Manager | Researcher | Analyst
hosting: company           # company | self | remote
auth_method: api_key       # api_key | cli | oauth
api_provider: openrouter   # openrouter | anthropic | custom
llm_model: ""              # Leave empty for platform default
temperature: 0.7
hiring_fee: 0.0            # USD, 0.0 = free
salary_per_1m_tokens: 0.0
skills:
  - skill-one
  - skill-two
personality_tags:
  - autonomous
  - thorough
system_prompt_template: >
  You are an AI agent that...
```

## Hosting Modes

- **company** — Platform-hosted, managed lifecycle via SubprocessExecutor
- **self** — Self-hosted, runs as independent Claude CLI process
- **remote** — External worker that connects via HTTP polling

## Skills

Each skill is a markdown file in `skills/`:

```markdown
# Skill Name

Instructions for the agent when this skill is activated.
Describe the task, constraints, and expected behavior.
```

## Agent Family

If your agent is based on a known framework, set `agent_family` in profile.yaml:

- `claude` — Claude Code agent
- `openclaw` — OpenClaw graph-based agent
- `omctalent` — OMC native agent
- Or any custom string

## License

MIT
