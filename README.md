# Hermes Agent Setup Guide

A complete, step-by-step guide to installing, configuring, and running [Hermes Agent](https://hermes-agent.nousresearch.com) — an open-source AI assistant that connects to WeChat, Telegram, and runs on your own hardware.

## What's Inside

| Chapter | Topic |
|---------|-------|
| 01 | What You're Building |
| 02 | One-Command Install |
| 03 | Multiple Provider Setup (Gemini, Grok, Claude, etc.) |
| 04 | WeChat & Telegram Integration |
| 05 | Server Deployment (Lighthouse, GCP, DigitalOcean) |
| 06 | systemd Auto-Start & Crash Recovery |
| 07 | Skills System |
| 08 | Security Hardening |
| 09 | 10 Automation Recipes (morning briefings, crypto alerts, RSS, etc.) |
| 10 | Config.yaml Deep Dive |
| 11 | Troubleshooting |

## Bonus Files

- `bonus/config.yaml` — Pre-configured config template
- `bonus/hermes.service` — systemd service file for auto-start
- `bonus/cron-recipes.yaml` — 8 ready-to-deploy cron job recipes

## Quick Start

```bash
pip install hermes-agent
hermes setup
```

Then follow [Chapter 01](ch01.md) for full setup instructions.

## Premium Edition

A print-ready PDF + DOCX version with cover page is available on [Gumroad](https://koksing.gumroad.com/l/xkrtq) (name your price, $15 suggested).

## License

This guide is provided for personal use. You're welcome to share the link to this repo, but please don't redistribute the content commercially without permission.
