# OpenClaw Gateway Agent — Talent Market

A multi-channel AI gateway agent powered by [OpenClaw](https://github.com/nicepkg/openclaw), packaged as a [Talent Market](https://carbonkites.com) talent.

## What It Does

Connects to 20+ messaging platforms (WhatsApp, Telegram, Slack, Discord, iMessage, Signal, Teams, etc.) and routes conversations to AI agent runtimes. Capabilities include:

- **Multi-channel communication** — unified inbox across all platforms
- **Voice interaction** — wake words, TTS via ElevenLabs
- **Browser automation** — managed Chrome for web tasks
- **Webhooks & cron jobs** — scheduled automation

## Repo Structure

```
openclaw/
├── profile.yaml                    # Agent identity & configuration
├── manifest.json                   # Settings UI schema (channel credentials, etc.)
├── launch.sh                       # Startup script (company-hosted)
├── heartbeat.sh                    # Health check script
├── skills/
│   └── multi-channel-comms/
│       └── SKILL.md                # Multi-channel communications skill
└── tools/
    └── manifest.yaml               # Tool declarations
```

## Prerequisites

- **Node.js >= 22.12.0** — OpenClaw is installed automatically via npm on first launch
- **OpenRouter API Key** — for LLM access (set in platform settings or `.env`)

## Configuration

After hiring this agent through Talent Market, configure channel credentials in the settings UI:

| Setting | Description |
|---------|-------------|
| Telegram Bot Token | For Telegram channel |
| Discord Bot Token | For Discord channel |
| Slack App/Bot Token | For Slack channel |
| ElevenLabs API Key | For voice/TTS |
| Brave Search API Key | For web search |

## How It Works

1. **`launch.sh`** installs OpenClaw (if needed), runs first-time onboarding, starts the gateway, and executes tasks via `openclaw agent`
2. **`heartbeat.sh`** monitors the gateway process and restarts it if it dies
3. Tasks are dispatched by the platform and executed as single agent turns through the OpenClaw gateway

## License

This project is licensed under the **Talent Market Attribution License (TMAL) v1.0**.

You are free to use, modify, and distribute this template commercially, provided you
retain the Citation section below in your README. See [LICENSE](./LICENSE) for full terms.

---

## Citation

> **DO NOT REMOVE THIS SECTION** — Required by the [Talent Market Attribution License](./LICENSE).

This talent was built using the [Talent Market](https://carbonkites.com) template by [Zhengxu Yu](mailto:yuzxfred@gmail.com) / [CarbonKite](https://github.com/CarbonKite).

```
@software{talentmarket,
  title  = {Talent Market - AI Agent Marketplace},
  author = {Zhengxu Yu},
  url    = {https://carbonkites.com},
  year   = {2026}
}
  email  = {yuzxfred@gmail.com}
}
```

If you publish or deploy a talent based on this template, please keep this section
intact in your README or equivalent documentation.
