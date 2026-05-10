# Hermes Agent: The Complete Setup & Automation Blueprint

## Build Your Own 24/7 AI Assistant on Your Server

---

## Table of Contents

1. [What You're Building](#chapter-1-what-youre-building)
2. [One-Command Install](#chapter-2-one-command-install)
3. [Multiple Provider Setup](#chapter-3-multiple-provider-setup)
4. [Connected Everywhere — WeChat, Telegram & More](#chapter-4-connected-everywhere)
5. [Server Choice & Real-World Deployment](#chapter-5-server-choice--real-world-deployment)
6. [systemd & Auto-Start Setup](#chapter-6-systemd--auto-start-setup)
7. [Skills System](#chapter-7-skills-system)
8. [Security Hardening](#chapter-8-security-hardening)
9. [Automation Recipes — 10 Copy-Paste Ready Workflows](#chapter-9-automation-recipes)
10. [Config.yaml Deep Dive](#chapter-10-configyaml-deep-dive)
11. [Troubleshooting Common Problems](#chapter-11-troubleshooting)

---

(Content from each chapter file follows below — compiled from ch01.md through ch11.md)

---

# Chapter 1: What You're Building — Your Personal AI Agent

> **"An AI agent you actually own, running on your own server, connected to your phone, working 24/7."**

Before we dive into installation, let's get crystal clear on what exactly you're building and why it's worth your time.

## 1.1 Hermes Agent vs. ChatGPT vs. Claude

Most people interact with AI through a web browser. You type something in, get an answer, close the tab. Here's what that looks like:

| | ChatGPT / Claude (Web) | **Hermes Agent** |
|---|---|---|
| Runs where? | Someone else's cloud | **Your own server** |
| Works when you're offline? | ❌ | ✅ Runs 24/7 |
| Talks to you on phone? | Web app only | **WeChat, Telegram, Discord** |
| Remembers you between chats? | Limited | **Permanent memory** |
| Can run commands on your server? | ❌ | ✅ Full shell access |
| Cost | $20/mo + API usage | **$5/mo VPS + pennies in API** |

**The key difference:** Hermes Agent is an *autonomous agent*, not just a chatbot. It can:

- **Schedule and execute tasks** — send you a daily news briefing every morning at 8 AM
- **Monitor things** — watch a website for changes, check stock prices, alert you
- **Run code** — write Python scripts, analyze data, manage files
- **Learn new skills** — teach it a workflow once, it remembers forever
- **Connect to everything** — email, calendar, smart home, GitHub, databases

Think of it as having a personal assistant that never sleeps, never takes a day off, and costs less than a Netflix subscription.

## 1.2 What You'll Have at the End of This Guide

By the time you finish this book, you will have:

```
┌──────────────────────────────────────────┐
│           YOUR HERMES AGENT              │
│                                          │
│  ┌─────────────┐    ┌──────────────────┐ │
│  │  WeChat      │    │  Telegram         │ │
│  │  (phone) ◄──┼────┼──► (phone/desk)  │ │
│  └──────┬──────┘    └────────┬─────────┘ │
│         │                    │            │
│  ┌──────▼────────────────────▼──────────┐ │
│  │        HERMES GATEWAY                │ │
│  │    (routes messages to agent)        │ │
│  └────────────────┬─────────────────────┘ │
│                   │                       │
│  ┌────────────────▼─────────────────────┐ │
│  │        HERMES AGENT CORE             │ │
│  │    • Memory (remembers everything)   │ │
│  │    • Skills (learns new abilities)   │ │
│  │    • Tools (web, files, terminal)    │ │
│  └────────────────┬─────────────────────┘ │
│                   │                       │
│  ┌────────────────▼─────────────────────┐ │
│  │       YOUR VPS (Linux Server)        │ │
│  │    • Runs 24/7, auto-restarts        │ │
│  │    • Costs ~$5-10/month              │ │
│  └──────────────────────────────────────┘ │
└──────────────────────────────────────────┘
```

## 1.3 What Makes Hermes Agent Special?

### Skills System

This is Hermes' superpower. When you teach your agent how to do something — or when it figures something out on its own — it saves that knowledge as a **skill**. Next time you need the same thing, it already knows how.

**Example:** You ask your agent to "check if any new GitHub releases mention my company name." The agent figures out the API calls, the search logic, the notification format. It saves this as a skill called `github-mention-watcher`. Tomorrow, you just say "run the watcher" and it works — no re-explaining needed.

### Persistent Memory

Hermes remembers who you are. Your preferences. Your environment. Things you taught it last week. It stores this in a memory system that survives restarts, reboots, and even server migrations.

### Multi-Platform

You talk to your agent through **WeChat** (from your phone), **Telegram** (from your desktop), and **CLI** (directly on the server). The same agent, the same memory, the same skills — different entry points.

### Provider Flexibility

You're not locked into any AI company. Use **OpenAI** today, switch to **Anthropic** tomorrow, use **Google Gemini** for free, fall back to **DeepSeek** when you're on a budget. The agent sees them all the same way.

## 1.4 Real Things People Do With Hermes

| Category | Example |
|----------|---------|
| **Daily briefings** | "Every morning at 8 AM, send me weather + top 3 news + my calendar" |
| **Website monitoring** | "Watch product X on Amazon and alert me when price drops below $50" |
| **Research assistant** | "Research competitors in my space and write a summary to this file" |
| **Content creation** | "Write a blog post from these notes and publish to WordPress" |
| **Financial tracking** | "Check my stock portfolio every Friday and send a summary" |
| **DevOps helper** | "Check disk usage, restart the web service if memory is high" |
| **Language learning** | "Send me 5 Japanese flashcards every evening" |
| **Email management** | "Summarize my inbox, flag urgent emails" |

## 1.5 The Cost Breakdown

Here's what this will actually cost you per month:

| Item | Cost | Notes |
|------|------|-------|
| VPS (Lighthouse / GCP / DigitalOcean) | **$5-10/mo** | Smallest tier is plenty |
| AI API usage (typical) | **$2-10/mo** | Gemini Flash is nearly free |
| **Total** | **~$7-20/mo** | Less than ChatGPT Plus |

If you're smart about which model you use (Gemini Flash for simple tasks, Claude for complex ones), you can keep this under **$10/month total**.

## 1.6 What You Need to Start

Before Chapter 2, make sure you have:

- [ ] A Linux server (VPS) — we'll cover this in Chapter 5
- [ ] An email address (for API account signups)
- [ ] A phone with WeChat or Telegram installed
- [ ] A credit/debit card (for the VPS — costs $5-10/mo)

That's it. No coding experience needed. If you can copy and paste commands, you can build this.

---

**Ready to build?** In Chapter 2, we'll do a one-command install and have your first conversation with Hermes.

---

# Chapter 2: One-Command Install — Your First Hermes Conversation

> **"No complicated setup. No missing dependencies. One command, and you're talking to your AI."**

Hermes Agent was designed to be installable with a single curl command. In this chapter, we'll get it running on your Linux server and have your first conversation — all in under 10 minutes.

## 2.1 Prerequisites

You need:
- A Linux server (Ubuntu 22.04 / Debian 12 recommended)
- Root or sudo access
- At least 1 GB RAM, 10 GB disk (the smallest VPS tier works)
- Python 3.10+ (most modern Linux distros have this)

> **Don't have a server yet?** Skip to Chapter 5 which covers setting up Tencent Cloud Lighthouse, GCP, and other VPS options. Then come back here.

## 2.2 The One-Command Install

SSH into your server, then run:

```bash
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
```

**What this does:**
1. Detects your OS and architecture
2. Creates a Python virtual environment at `~/.hermes/hermes-agent/venv/`
3. Installs Hermes Agent and all Python dependencies
4. Sets up the `hermes` command in your PATH

When it finishes, you'll see something like:

```
✅ Hermes Agent installed successfully!
Run 'hermes' to start chatting.
```

### If the command isn't found after install

The installer adds Hermes to your shell profile, but it won't take effect in the current session. Run this to activate it:

```bash
source ~/.bashrc
```

Or log out and SSH back in.

> **⚠️ Common pitfall:** Some VPS providers ship minimal images without `curl`. If you get "command not found: curl", install it first:
>
> ```bash
> sudo apt update && sudo apt install curl -y   # Ubuntu/Debian
> ```
>
> For CentOS/RHEL: `sudo yum install curl -y`

## 2.3 Your First Conversation

Just type:

```bash
hermes
```

You'll see a welcome banner, and Hermes will verify your environment. Then type anything you want.

```
╭──────────────────────────────────────────╮
│           Hermes Agent v0.x.x            │
│     Your autonomous AI assistant         │
╰──────────────────────────────────────────╯
Model: Not configured
Provider: Not configured
Type '/help' for available commands.

You: Hello! What can you do?
```

If it asks you to configure a model first (because no API key is set), that's fine — we'll do that in the next chapter. But if you already have an API key set in your environment, Hermes will start working immediately.

### Quick test queries to try:

```
What's the current date and time?
Show me disk space on this server
List the files in my home directory
What's my IP address?
```

## 2.4 Exiting Hermes

```bash
/quit
```

Or press `Ctrl+C` / `Ctrl+D`.

## 2.5 Understanding What Just Installed

Here's what's now on your server:

```
~/.hermes/                          # Hermes home directory
├── config.yaml                     # Your configuration
├── .env                            # API keys (you'll create this)
├── hermes-agent/                   # Source code
│   ├── venv/                       # Python virtual environment
│   └── ...                         # The agent code
├── skills/                         # Installed skills
├── sessions/                       # Chat history
└── logs/                           # Error logs
```

**Key paths to remember:**
- `~/.hermes/config.yaml` — main configuration file
- `~/.hermes/.env` — API keys and secrets (never share this!)
- `~/.hermes/sessions/` — all your conversations are saved here

## 2.6 Updating Hermes

Updates come out regularly with new features and fixes:

```bash
hermes update
```

Or to check your current version:

```bash
hermes --version
```

## 2.7 Uninstalling (Just in Case)

If you ever need to remove it:

```bash
hermes uninstall
```

This removes the `~/.hermes/` directory and the `hermes` command.

---

**You just installed an AI agent on your own server.** That's the hardest part — everything from here is configuration and customization.

In **Chapter 3**, we'll connect Hermes to an AI provider so it can actually think and respond. You'll learn how to set up OpenAI, Anthropic, Google Gemini, OpenRouter, and even use them together with automatic fallback.

---

# Chapter 3: Multiple Provider Setup — Pick Your Brain

> **"The best part of Hermes: you're not locked into any AI company. Switch models like changing TV channels."**

Hermes works with over 20 AI providers. You can use any of them — or several at once with automatic fallback. This chapter covers the most popular ones step by step.

## 3.1 How Providers Work in Hermes

You need two things:

1. **An API key** — from the AI provider (OpenAI, Anthropic, Google, etc.)
2. **Configuration** — tell Hermes which provider and model to use

All API keys go in `~/.hermes/.env`. All settings go in `~/.hermes/config.yaml` (or use the interactive model picker).

> **Security rule:** Never put API keys directly in `config.yaml`. Always use the `.env` file. The `.env` file should never be shared or committed to GitHub.

## 3.2 Option A: Google Gemini (Best Free Option)

**Why choose this:** Gemini 2.5 Flash is extremely capable and has a generous free tier. I use this as my primary provider.

### Step 1: Get an API key

1. Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
2. Click **"Create API Key"**
3. Copy the key (it starts with `AIza...`)

### Step 2: Add to your server

SSH in and run:

```bash
echo 'GOOGLE_API_KEY=your_key_here' >> ~/.hermes/.env
```

Replace `your_key_here` with the actual key you copied.

### Step 3: Configure Hermes

Run the interactive model picker:

```bash
hermes model
```

Navigate to **Google**, select **Gemini 2.5 Flash**, and confirm.

Or set it directly:

```bash
hermes config set model.provider google
hermes config set model.default gemini-2.5-flash
```

### Verify it works:

```bash
hermes chat -q "Hello! What model are you using?"
```

It should respond and mention Gemini.

## 3.3 Option B: OpenRouter (One Key for 200+ Models)

**Why choose this:** One API key gives you access to every major model — Claude, GPT-4, Gemini, DeepSeek, Llama, Mistral, and many more. You pay per-use, per-model.

### Step 1: Get an API key

1. Go to [openrouter.ai/keys](https://openrouter.ai/keys)
2. Sign up and create a key
3. Add $5-10 credit (lasts months for typical use)

### Step 2: Add to `.env`

```bash
echo 'OPENROUTER_API_KEY=sk-or-v1-your_key_here' >> ~/.hermes/.env
```

### Step 3: Configure

```bash
hermes config set model.provider openrouter
hermes config set model.default openai/gpt-4o-mini
```

Available models include:
- `openai/gpt-4o-mini` — cheap and fast (~$0.15/million tokens)
- `openai/gpt-4o` — most capable OpenAI model
- `anthropic/claude-sonnet-4` — best for coding
- `anthropic/claude-haiku-4` — fast and cheap
- `google/gemini-2.5-flash` — free tier available
- `deepseek/deepseek-chat` — very cheap, good quality
- `meta-llama/llama-3-8b` — open-source, runs fast

## 3.4 Option C: Anthropic Claude (Best for Coding)

**Why choose this:** Claude Sonnet 4 is arguably the best model for programming and complex reasoning tasks.

### Step 1: Get an API key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up and generate an API key
3. Add credit ($5-20 depending on usage)

### Step 2: Add to `.env`

```bash
echo 'ANTHROPIC_API_KEY=sk-ant-your_key_here' >> ~/.hermes/.env
```

### Step 3: Configure

```bash
hermes config set model.provider anthropic
hermes config set model.default claude-sonnet-4
```

## 3.5 Option D: OpenAI (GPT-4)

### Step 1: Get an API key

1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Create a new key
3. Add credit (requires a paid account)

### Step 2: Add to `.env`

```bash
echo 'OPENAI_API_KEY=sk-your_key_here' >> ~/.hermes/.env
```

### Step 3: Configure

```bash
hermes config set model.provider openai
hermes config set model.default gpt-4o
```

## 3.6 Option E: Custom / Local Models

If you're running a local LLM (via Ollama, llama.cpp, vLLM, etc.), point Hermes to it:

```bash
hermes config set model.provider custom
hermes config set model.base_url http://localhost:11434/v1  # Ollama example
hermes config set model.default llama3.1
```

## 3.7 Advanced: Multi-Provider Fallback

This is where Hermes really shines. You can set up a **primary model** and **fallback models** — if the primary fails (rate limit, outage, etc.), Hermes automatically tries the next one.

Edit `~/.hermes/config.yaml` and set:

```yaml
model:
  provider: openrouter
  default: openai/gpt-4o-mini
  fallbacks:
    - provider: google
      model: gemini-2.5-flash
    - provider: anthropic
      model: claude-haiku-4
```

Now your agent tries GPT-4o-mini first. If OpenRouter is down, it switches to Gemini. If Gemini is unavailable, it falls back to Claude. Your agent never goes silent.

## 3.8 Cost Comparison

| Model | Cost per 1M input tokens | Good for |
|-------|--------------------------|----------|
| **Gemini 2.5 Flash** | Free tier → $0.15 | Everyday tasks, fast response |
| **Claude Haiku 4** | ~$0.80 | Quick answers, classification |
| **GPT-4o mini** | ~$0.15 | General use, very cheap |
| **DeepSeek Chat** | ~$0.27 | Coding, analysis |
| **Claude Sonnet 4** | ~$3.00 | Complex coding, deep reasoning |
| **GPT-4o** | ~$2.50 | General purpose premium |
| **Claude Opus 4** | ~$15.00 | Maximum capability |

**My recommendation for you:** Start with **Gemini 2.5 Flash** (free tier covers most needs) and add **OpenRouter** for when you need Claude's coding abilities.

## 3.9 Quick Config Cheat Sheet

```bash
# Set provider
hermes config set model.provider openrouter

# Set default model
hermes config set model.default openai/gpt-4o-mini

# Set environment variable (replace KEY with actual)
echo 'PROVIDER_API_KEY=your_key' >> ~/.hermes/.env

# Verify everything
hermes doctor

# Test
hermes chat -q "Hello! Who are you?"
```

---

**In Chapter 4**, we'll connect Hermes to WeChat so you can talk to your agent from your phone. This is where it gets really fun — your personal AI assistant in your pocket, 24/7.

---

# Chapter 4: Connected Everywhere — WeChat, Telegram & More

> **"Your AI agent in your pocket. Text it from anywhere, anytime."**

A CLI-only AI agent is useful. An AI agent you can text from your phone while grocery shopping? That's a game changer.

This chapter covers:
- **WeChat** (Weixin) — works on your phone and MacBook
- **Telegram** — the easiest option, works everywhere
- **CLI tips** — when you're at your computer

## 4.1 The Gateway: How It Works

Hermes uses something called the **Gateway**. Think of it as a traffic controller:

```
Your message (WeChat/Telegram)
        │
        ▼
    ┌──────────┐
    │ Gateway   │ ───► Hermes Agent
    └──────────┘       (processes, thinks, acts)
        │
        ▼
Response back to you
```

The Gateway runs as a **background service** on your server. It listens for incoming messages from WeChat, Telegram, or other platforms, feeds them to Hermes, and sends the response back.

## 4.2 Setting Up WeChat (Weixin)

WeChat support in Hermes works through the official Weixin (微信) platform. Here's how to set it up:

### Prerequisites

- A WeChat/Weixin account (you already have one)
- A WeChat Official Account (服务号) — required for bot functionality
- The Gateway service running on your server

### Step 1: Create a WeChat Official Account

1. Go to [mp.weixin.qq.com](https://mp.weixin.qq.com)
2. Register a **Service Account (服务号)** — this is the type that supports API access
3. Complete the verification process (may take 1-3 business days)

### Step 2: Configure in Hermes Gateway

Run the gateway setup wizard:

```bash
hermes gateway setup
```

Select **Weixin** and follow the prompts. You'll need:
- Your AppID and AppSecret (from the WeChat Official Account dashboard)
- A token (you create this yourself — anything, just remember it)
- Your server's public IP or domain name

### Step 3: Configure the Webhook URL

In your WeChat Official Account dashboard:
1. Go to **Settings** → **Development** → **Basic Configuration**
2. Set the **Server URL** to: `http://your-server-ip:9090/webhooks/weixin`
3. Set the **Token** to match what you configured in Hermes
4. Choose **AES-256** encryption mode
5. Submit (WeChat will send a verification request — Hermes handles it automatically)

### Step 4: Start the Gateway

```bash
hermes gateway start
```

Check it's running:

```bash
hermes gateway status
```

### Step 5: Scan to Chat

Go to your WeChat Official Account and send a message. If everything's set up correctly, you'll get a response from your Hermes Agent.

> **⚠️ Common issue:** WeChat Official Accounts outside mainland China may have restrictions. If you can't get a Service Account, use the **Telegram** method below instead — it's simpler and works globally.

## 4.3 Setting Up Telegram (Simpler Alternative)

Telegram is the easiest messaging platform to set up with Hermes. It takes about 5 minutes.

### Step 1: Create a Telegram Bot

1. Open Telegram and search for **@BotFather** (the official bot that creates bots)
2. Start a chat and send: `/newbot`
3. Choose a name (e.g., "My Hermes Agent")
4. Choose a username (must end in `bot`, e.g., `my_hermes_bot`)
5. BotFather will give you a **token** — save this!

### Step 2: Configure in Hermes

Run:

```bash
hermes gateway setup
```

Select **Telegram** and paste your bot token when prompted.

### Step 3: Start the Gateway

```bash
hermes gateway start
```

### Step 4: Talk to Your Bot

Open Telegram, search for your bot's username, and send a message. Your Hermes Agent will respond.

That's it. No webhooks, no domain names, no verification delays. Telegram is truly plug-and-play.

## 4.4 The CLI: When You're at Your Computer

Sometimes you want to interact directly on the server. The CLI is great for:

- **Quick queries** without pulling out your phone:
  ```bash
  hermes chat -q "What's the disk usage on this server?"
  ```

- **Running background tasks**:
  ```bash
  hermes chat -q "Research RAG techniques and save summary to ~/rag-notes.md"
  ```

- **Administration** — configuring providers, managing skills, checking logs

### Useful CLI Flags

```bash
hermes                       # Interactive chat session
hermes chat -q "query"       # One-shot question, non-interactive
hermes --continue            # Resume your last session
hermes -s skill-name         # Load a skill at startup
```

## 4.5 Pro Tip: Configure Per-Platform Settings

You can have different settings for different platforms. For example, use a cheap model for WeChat (quick answers) and a powerful model for CLI (complex tasks).

```bash
hermes skills config  # Shows platform-specific skill settings
```

This is covered in detail in Chapter 8 (Configuration Mastery).

## 4.6 Gateway Troubleshooting

### Gateway won't start

Check the logs:

```bash
cat ~/.hermes/logs/gateway.log | tail -20
```

Most common causes:
- Missing API keys in `.env`
- Port already in use (change port in `config.yaml`)
- Python dependencies not installed (run `hermes doctor`)

### Gateway stops when I log out of SSH

You need to enable "lingering" for systemd user services:

```bash
sudo loginctl enable-linger $USER
```

This keeps systemd services running after you disconnect SSH.

### Messages work but no response

Run `hermes doctor` to check for configuration issues:

```bash
hermes doctor
```

---

**Your Hermes Agent is now on your phone.** Try sending it a message from the supermarket: "Add milk and eggs to my shopping list." It remembers, because in Chapter 7, we cover the Skills System — the feature that makes Hermes learn and improve over time.

---

# Chapter 5: Server Choice & Real-World Deployment

> **"Theory is great. But let me show you exactly what I run — two servers, two clouds, all working."**

I run Hermes on two different cloud providers. In this chapter, I'll walk you through both setups so you can choose what works best for you.

## 5.1 What Makes a Good Hermes Server

Hermes is lightweight. Here's the minimum:

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| CPU | 1 core | 2 cores |
| RAM | 512 MB | 1-2 GB |
| Storage | 5 GB | 10-20 GB |
| OS | Ubuntu 20.04+ | Ubuntu 22.04 LTS |
| Network | Public IP | Public IP + domain |

**Cost range:** $4-12/month, depending on provider and region.

## 5.2 Option A: Tencent Cloud Lighthouse (My Setup)

I run Hermes on a Tencent Cloud Lighthouse instance. It's good value if you're in Asia.

### Create the instance

1. Go to [console.cloud.tencent.com/lighthouse](https://console.cloud.tencent.com/lighthouse)
2. Click **Create Instance**
3. Choose:
   - **Region:** Closest to you (e.g., Singapore, Hong Kong)
   - **Image:** Ubuntu 22.04 LTS
   - **Plan:** The cheapest tier ($5-6/month) is sufficient
4. Set a **strong password** (save this!) or upload an SSH key
5. Click **Buy Now**

### Configure SSH access

From your local machine:

```bash
ssh root@your-lighthouse-ip
```

Enter the password you set during creation.

### Install Hermes

```bash
# 1. Update the system
apt update && apt upgrade -y

# 2. Install curl (if missing)
apt install curl -y

# 3. Install Hermes
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# 4. Reload shell
source ~/.bashrc
```

### Start chatting

```bash
hermes
```

> **Note:** On Lighthouse, the default user is `root`. Hermes can run as root without issues, but for better security, consider creating a non-root user:
>
> ```bash
> adduser agentuser
> usermod -aG sudo agentuser
> # Then SSH as agentuser and install Hermes from that account
> ```

## 5.3 Option B: Google Cloud Platform (My Second Setup)

I also run Hermes on GCP. This is a good option if you need Google Cloud's network or want to use other GCP services.

### Create the VM

1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Navigate to **Compute Engine** → **VM Instances**
3. Click **Create Instance**
4. Configure:
   - **Name:** `hermes-agent` (or anything)
   - **Region/Zone:** Closest to you
   - **Machine type:** `e2-micro` (free tier eligible!) or `e2-small` (~$12/mo)
   - **Boot disk:** Ubuntu 22.04 LTS, 10 GB standard persistent disk
   - **Firewall:** Allow HTTP and HTTPS traffic
5. Click **Create**

### SSH into the VM

From the GCP Console, click the **SSH** button next to your VM. Or from your local terminal:

```bash
gcloud compute ssh hermes-agent
```

### Install Hermes

Same process as above:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl -y
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
source ~/.bashrc
```

### Cost-Saving Tip: Preemptible VMs

On GCP, you can use **preemptible (spot) VMs** which cost 60-80% less. The downside: they can be terminated with 30 seconds notice. This is fine if you don't need 100% uptime.

To protect against termination, set up a systemd service for Hermes (covered in Chapter 6) — it auto-restarts when the VM comes back.

## 5.4 Option C: DigitalOcean (Simplest)

DigitalOcean is the easiest VPS provider if you're outside Asia.

1. Go to [digitalocean.com](https://digitalocean.com)
2. Create a **Droplet**:
   - **OS:** Ubuntu 22.04 LTS
   - **Plan:** $6/mo (1 GB RAM, 1 CPU, 25 GB SSD)
   - **Region:** Closest to you
3. Add your SSH key
4. Create the Droplet
5. SSH in and follow the install steps above

## 5.5 Security Basics

Whichever provider you choose, do these as soon as your server is running:

### 1. Update everything

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Set up a firewall

```bash
sudo ufw allow OpenSSH
sudo ufw enable
```

If you're running the Gateway:
```bash
sudo ufw allow 9090  # Hermes Gateway default port
```

### 3. Disable root password login (SSH key only)

```bash
# On your local machine, generate a key if you don't have one:
ssh-keygen -t ed25519

# Copy it to the server:
ssh-copy-id root@your-server-ip

# On the server, edit SSH config:
sudo nano /etc/ssh/sshd_config

# Set these:
# PermitRootLogin prohibit-password
# PasswordAuthentication no

# Restart SSH:
sudo systemctl restart sshd
```

### 4. Store API keys safely

All API keys go in `~/.hermes/.env`. Set restrictive permissions:

```bash
chmod 600 ~/.hermes/.env
```

## 5.6 Provider Selection Guide

| If you're in... | Recommend |
|----------------|-----------|
| Asia | Tencent Cloud Lighthouse ($5/mo) |
| Anywhere | GCP e2-micro (free tier) |
| Anywhere | DigitalOcean ($6/mo) |
| Europe | Hetzner Cloud ($4/mo — cheapest option) |
| US | Linode / Vultr ($5/mo) |

## 5.7 Verification Checklist

After setting up your server:

- [ ] Can SSH into the server
- [ ] `hermes` command starts the interactive session
- [ ] API key is set in `~/.hermes/.env`
- [ ] Model responds to queries
- [ ] Firewall is active
- [ ] SSH key authentication works
- [ ] `chmod 600 ~/.hermes/.env` is set

---

**Your Hermes Agent now lives on a server that runs 24/7.** In Chapter 6, we set it up as a proper background service so it auto-starts on reboot and never goes down.

---

# Chapter 6: systemd & Auto-Start Setup

> **"Set it and forget it — your agent starts itself, even after a reboot."**

One of the best things about running your own AI agent is that it's always on. But what happens when your server restarts? A power outage? A routine update that reboots the machine?

Without auto-start, you'd have to SSH in and manually run `hermes` every time. That defeats the purpose of a 24/7 agent.

In this chapter, you'll learn how to set up Hermes Agent as a **systemd service** — so it starts automatically when your server boots, restarts if it crashes, and logs everything properly.

## 6.1 Why systemd?

systemd is the init system used by virtually all modern Linux distributions (Ubuntu 20.04+, Debian 10+, CentOS 7+). It manages services, their dependencies, and their lifecycles.

| Approach | Auto-start on boot? | Crash recovery? | Logging? | Effort |
|---|---|---|---|---|
| **systemd service** | ✅ | ✅ | ✅ journald | ~5 minutes |
| crontab @reboot | ✅ | ❌ Manual restart | ❌ | ~2 minutes |
| tmux/screen session | ❌ | ❌ | ❌ | ~1 minute |
| Docker | ✅ | ✅ | ✅ | Advanced |

**systemd is the gold standard.** It's built into your OS, requires no extra dependencies, and gives you the best reliability.

## 6.2 Creating the systemd Service File

First, find where Hermes is installed. Run this on your server:

```bash
which hermes
```

Typical output: `/home/agentuser/.hermes/hermes-agent/venv/bin/hermes`

Also find the user that runs Hermes (you should **not** run it as root):

```bash
whoami
```

Now create the service file:

```bash
sudo tee /etc/systemd/system/hermes.service << 'EOF'
[Unit]
Description=Hermes AI Agent
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
User=agentuser
WorkingDirectory=/home/agentuser
ExecStart=/home/agentuser/.hermes/hermes-agent/venv/bin/hermes
Restart=on-failure
RestartSec=10
StandardOutput=journal
StandardError=journal
Environment="PATH=/home/agentuser/.hermes/hermes-agent/venv/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
Environment="HOME=/home/agentuser"

[Install]
WantedBy=multi-user.target
EOF
```

> **Note:** Replace `agentuser` with your actual username, and adjust the `ExecStart` path to match the output from `which hermes`.

### Key settings explained:

| Setting | What it does |
|---|---|
| `After=network-online.target` | Waits for the network to be fully up before starting |
| `Restart=on-failure` | Auto-restarts Hermes if it crashes (non-zero exit) |
| `RestartSec=10` | Waits 10 seconds before restarting (prevents restart loops) |
| `StandardOutput=journal` | Sends logs to systemd's journal (viewable with `journalctl`) |
| `Environment=PATH=...` | Ensures the venv's Python is found even on reboot |

## 6.3 Enabling and Starting the Service

After creating the file, run:

```bash
# Reload systemd to pick up the new service
sudo systemctl daemon-reload

# Enable auto-start on boot
sudo systemctl enable hermes.service

# Start it now
sudo systemctl start hermes.service

# Check status
sudo systemctl status hermes.service
```

You should see output like:

```
● hermes.service - Hermes AI Agent
     Loaded: loaded (/etc/systemd/system/hermes.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2026-04-30 09:00:00 UTC; 10s ago
   Main PID: 12345 (hermes)
      Tasks: 2 (limit: 2345)
     Memory: 48.5M
        CPU: 1.234s
```

If you see `active (running)`, congratulations — Hermes is now running as a system service!

## 6.4 Managing the Service Day-to-Day

Once set up, you manage Hermes with simple systemd commands:

```bash
# Check status
sudo systemctl status hermes.service

# Restart (useful after config changes)
sudo systemctl restart hermes.service

# Stop
sudo systemctl stop hermes.service

# Start
sudo systemctl start hermes.service

# Check if it's set to auto-start
sudo systemctl is-enabled hermes.service
```

## 6.5 Viewing Logs

Logs go to systemd's journal, not a file. View them with:

```bash
# Follow logs in real-time (like tail -f)
sudo journalctl -u hermes.service -f

# Last 50 lines
sudo journalctl -u hermes.service -n 50

# All logs from today
sudo journalctl -u hermes.service --since today

# All logs with timestamps
sudo journalctl -u hermes.service --output short-precise
```

To keep logs from growing forever, set a max size:

```bash
sudo journalctl --vacuum-time=7d
```

This keeps only the last 7 days of logs. Add it to a monthly cron job if you want automatic cleanup.

## 6.6 Testing Auto-Restart

Test that crash recovery works:

```bash
# Find the PID
sudo systemctl status hermes.service | grep "Main PID"

# Kill the process (simulates a crash)
sudo kill <PID>

# Wait a moment, then check — it should have restarted
sleep 15
sudo systemctl status hermes.service
```

You should see `Active: active (running)` with a new PID and a note that it was restarted.

## 6.7 Testing Reboot Recovery

This is the big one — does it survive a full reboot?

```bash
# Schedule a reboot in 1 minute
sudo shutdown -r +1
```

Wait 2 minutes, then SSH back in and check:

```bash
sudo systemctl status hermes.service
```

Expected: `active (running)` with the uptime matching when your server came back up.

## 6.8 Troubleshooting systemd Issues

### "Unit hermes.service not found"

You created the file but forgot to reload systemd:

```bash
sudo systemctl daemon-reload
```

### "Failed to start: Unit hermes.service not found" after reboot

The service is enabled but the file is missing. Check it's in the right place:

```bash
ls -la /etc/systemd/system/hermes.service
```

If missing, re-create it (see section 6.2).

### Service starts then immediately stops

Check the logs:

```bash
sudo journalctl -u hermes.service -n 30 --no-pager
```

Common causes:
- **Wrong path** — `ExecStart` points to a file that doesn't exist
- **Wrong user** — the configured user doesn't have permissions
- **venv not activated** — the `PATH` environment doesn't include the venv's bin directory
- **Config error** — Hermes fails to parse `config.yaml`

Fix the issue, then:

```bash
sudo systemctl restart hermes.service
```

### "Restart loop" — service keeps restarting every 10 seconds

If Hermes keeps crashing immediately, it will keep restarting. systemd detects this after a few attempts and backs off:

```bash
# See how many times it's tried
sudo systemctl status hermes.service
# Look for "Main PID" — if it says "(limit 5min 0s)" it's in a restart hold

# Fix the underlying issue, then manually reset the failure count
sudo systemctl reset-failed hermes.service
sudo systemctl restart hermes.service
```

## 6.9 Alternative: Using tmux (No systemd)

If your server doesn't use systemd (very old distros, Docker containers), you can use tmux instead:

```bash
# Install tmux
sudo apt install tmux -y

# Create a detached session running Hermes
tmux new-session -d -s hermes

# Send the command to run Hermes
tmux send-keys -t hermes "hermes" Enter

# Reattach to see the output
tmux attach -t hermes

# Detach: Ctrl+B, then D
```

> **Caveat:** tmux does **not** auto-start on boot or auto-restart on crash. You'd need a cron `@reboot` entry to launch it.

## 6.10 Bonus: Multi-Instance Setup (Advanced)

Want to run multiple Hermes instances with different configs?

```bash
sudo tee /etc/systemd/system/hermes-work@.service << 'EOF'
[Unit]
Description=Hermes AI Agent (%i)
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
User=agentuser
WorkingDirectory=/home/agentuser
ExecStart=/home/agentuser/.hermes/hermes-agent/venv/bin/hermes --config /home/agentuser/.hermes/config-%i.yaml
Restart=on-failure
RestartSec=10

[Install]
WantedBy=multi-user.target
EOF
```

Then start instances by name:

```bash
sudo systemctl enable hermes-work@personal.service
sudo systemctl start hermes-work@personal.service

sudo systemctl enable hermes-work@work.service
sudo systemctl start hermes-work@work.service
```

Each instance reads a different config file (`config-personal.yaml`, `config-work.yaml`).

---

**Chapter Summary:**
- ✅ systemd automatically starts Hermes on boot and restarts it after crashes
- ✅ The service file goes in `/etc/systemd/system/hermes.service`
- ✅ Logs are managed via `journalctl`, not log files
- ✅ Test both crash recovery and reboot recovery before moving on
- ✅ Multi-instance setup available for advanced users

**Next up:** Chapter 7 — Skills System

---

# Chapter 7: Skills System — How Your Agent Gets Smarter Over Time

> **"The single feature that makes Hermes Agent more powerful than any chatbot: it learns."**

## 7.1 What Are Skills?

Skills are **reusable procedures** that Hermes saves and remembers. When you teach your agent how to do something once, it can do it again without being re-taught.

Think of skills like recipes in a cookbook:
- A recipe tells you how to make a dish
- A skill tells Hermes how to accomplish a task
- Once saved, anyone (you or your agent) can use it

### Real Example

**Without skills:**
> You: "Check if Amazon dropped the price on this laptop."
> Hermes: *scrapes Amazon, checks price, reports back*

**Next time you ask:**
> You: "Check if Amazon dropped the price on this laptop."
> Hermes: *has to figure it out all over again*

**With skills:**
> You: "Check if Amazon dropped the price on this laptop. Save this as a skill called 'price-watch'."
> Hermes: *does the work, saves the procedure*

**Next time you ask:**
> You: "Run price-watch on the new iPhone."
> Hermes: *already knows the steps. Instant.*

## 7.2 How Skills Work Under the Hood

A skill is just a markdown file with a special format:

```
~/.hermes/skills/
├── price-watch/
│   ├── SKILL.md           # The procedure description
│   └── references/         # Optional helper files
│       └── config.yaml
├── daily-briefing/
│   └── SKILL.md
└── research-agent/
    └── SKILL.md
```

Each `SKILL.md` contains:
1. **Metadata** — name, description, tags
2. **Instructions** — step-by-step what to do
3. **Edge cases** — what to watch out for

When you load a skill, Hermes reads this file and follows the instructions. It's like giving your agent a checklist + manual.

## 7.3 Loading a Skill

During a chat session:

```
/skill price-watch
```

Or at startup:

```bash
hermes -s price-watch,daily-briefing
```

## 7.4 Building Your First Skill

Let's create a skill that does something useful: a **daily briefing** that sends you weather + news every morning.

Create the skill directory and file:

```bash
mkdir -p ~/.hermes/skills/daily-briefing
nano ~/.hermes/skills/daily-briefing/SKILL.md
```

Paste this content:

```markdown
---
name: daily-briefing
description: Sends a morning briefing with weather, news, and reminders
tags: [daily, briefing, weather, news]
---

# Daily Briefing Skill

## When to use
- Every morning when the user says "send the briefing"
- Scheduled via cron to run at 7 AM daily

## What to do

1. **Get the weather:**
   - Use `web_search` to find today's weather for the user's city
   - If city unknown, check memory or ask

2. **Get top news:**
   - Search for top 3 news headlines
   - Summarize each in 1 sentence

3. **Check calendar (if connected):**
   - List any events for today

4. **Format the response:**
   - Title: "☀️ Good Morning! Here's your briefing:"
   - Section 1: Weather (emoji + temp + conditions)
   - Section 2: News (3 bullet points)
   - Section 3: Calendar (events, if any)

5. **Deliver:**
   - Send back to the user's home channel
```

Now test it:

```bash
hermes -s daily-briefing
```

Then ask: *"Run the daily briefing."*

## 7.5 Installing Community Skills

Hermes has a catalog of community-created skills. Browse them:

```bash
hermes skills browse
```

Or search:

```bash
hermes skills search automation
```

Install one:

```bash
hermes skills install <skill-id>
```

### Popular community skills to try:

| Skill | What it does |
|-------|-------------|
| `systematic-debugging` | Root-cause debugging framework |
| `writing-plans` | Creates implementation plans |
| `test-driven-development` | TDD workflow |
| `github-code-review` | PR code review automation |

## 7.6 Auto-Learning: How Hermes Creates Skills on Its Own

Here's the powerful part: Hermes can save skills **automatically**. After completing a complex task (5+ tool calls), you can tell it:

> "Save that as a skill."

Or it can detect that a workflow is worth saving. When it does, it creates a `SKILL.md` with:
- The problem it solved
- The steps it took
- The tools it used
- Pitfalls to avoid

This means over time, your agent gets better and better at *your* specific tasks.

## 7.7 Enabling/Disabling Skills

Some skills should only run on certain platforms:

```bash
hermes skills config
```

This lets you:
- Enable research skills only in CLI
- Disable destructive skills on WeChat
- Keep productivity skills everywhere

## 7.8 Skill Management Cheat Sheet

```bash
hermes skills list                  # See all installed skills
hermes skills search <query>        # Search skill catalog
hermes skills install <id>          # Install from catalog
hermes skills update                # Update all outdated skills
hermes skills check                 # Check for updates
hermes skills config                # Per-platform skill settings
/skill <name>                       # Load a skill mid-session
```

## 7.9 What to Teach Your Agent First

Here are 5 skills worth creating on day one:

1. **daily-briefing** — weather + news + calendar every morning
2. **web-researcher** — given a topic, produce a structured report
3. **file-organizer** — clean up downloads, sort by type/date
4. **server-health** — check disk, memory, uptime, send report
5. **note-taker** — save meeting notes to a formatted file

---

**This is what separates Hermes from every other AI tool.** Your agent doesn't just answer questions — it gets better over time. Every task you teach it makes the next one faster.

Chapter 8 covers Configuration Mastery — the full `config.yaml` breakdown, per-channel settings, model fallbacks, and credential pools.

---

# Chapter 8: Security Hardening

> **"Keep your agent safe — and your server safer."**

Running an AI agent on your own server means you're responsible for its security. A compromised Hermes Agent could read your files, access your API keys, or send messages from your accounts.

This chapter covers practical security measures — not paranoid ones. These are steps I've implemented myself across two production servers.

## 8.1 The Threat Model

Let's be realistic about what we're protecting against:

| Threat | Risk Level | How to Mitigate |
|---|---|---|
| Someone gains SSH access to your server | 🔴 High | Key-only auth, fail2ban, disable root login |
| An LLM provider API key is leaked | 🟡 Medium | Separate keys per service, restrict permissions |
| A malicious skill destroys data | 🟡 Medium | Run Hermes as non-root, filesystem isolation |
| Your agent's memory is exposed | 🟡 Medium | Encrypt sensitive data in config |
| DDoS/rate-limit abuse of your gateway | 🟢 Low | Rate limiting in config |

**The golden rule:** Treat Hermes like any other server daemon — least privilege, regular updates, monitored access.

## 8.2 Run Hermes as a Non-Root User

This is the single most important step. Never run Hermes as root.

```bash
# Create a dedicated user
sudo useradd -m -s /bin/bash hermes-agent

# Add to necessary groups (docker, etc. if needed)
sudo usermod -aG docker hermes-agent

# Switch to the user and install Hermes
sudo -u hermes-agent bash -c "$(curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh)"
```

If you already installed as another user (like `agentuser`), that's fine — just ensure that user has no special privileges like passwordless sudo.

**Check your current user's privileges:**

```bash
sudo -l
```

If you see `(ALL) NOPASSWD: ALL`, that user can run anything without a password. This is risky. If Hermes is ever compromised, the attacker has full root access.

**Fix it:**

```bash
# Remove passwordless sudo
sudo visudo -f /etc/sudoers.d/90-cloud-init-users
```

Remove or comment out the `NOPASSWD` line. Replace it with:

```
agentuser ALL=(ALL) PASSWD: ALL
```

## 8.3 API Key Security

Your Hermes config contains API keys for your LLM providers. These are valuable — losing them means someone else could use them at your expense.

### Store keys securely

**Recommended:** Use environment variables for sensitive fields.

Edit your `~/.hermes/config.yaml` and replace actual keys with placeholders:

```yaml
providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"
    model: openrouter/anthropic/claude-sonnet-4
  gemini:
    api_key: "${GEMINI_API_KEY}"
    model: gemini/gemini-2.5-flash
```

Then set them in `~/.bashrc` or a dedicated `.env` file:

```bash
# In ~/.bashrc, add:
export OPENROUTER_API_KEY="sk-or-v1-your-key-here"
export GEMINI_API_KEY="AIzaSy-your-key-here"
```

For systemd (from Chapter 6), inject environment variables via a secure drop-in:

```bash
sudo mkdir -p /etc/systemd/system/hermes.service.d/

sudo tee /etc/systemd/system/hermes.service.d/env.conf << 'EOF'
[Service]
Environment=OPENROUTER_API_KEY=sk-or-v1-your-key-here
Environment=GEMINI_API_KEY=AIzaSy-your-key-here
EOF

sudo systemctl daemon-reload
sudo systemctl restart hermes.service
```

> **Warning:** This stores keys in plaintext in the systemd drop-in file. For production, consider systemd-creds or a secrets manager (see section 8.6).

### Restrict API keys

Most LLM providers let you create **project-scoped** or **usage-limited** keys:

- **OpenRouter:** Create keys with a monthly spending cap ($5, $10, etc.)
- **Google Gemini:** API keys are project-scoped by default
- **OpenAI:** Create project keys (not org-wide keys) with usage limits
- **Anthropic:** Use workspace-specific API keys

Never use an org-admin API key for Hermes. Create a dedicated key with minimum necessary access.

## 8.4 SSH Hardening

Your server's SSH configuration is the front door. Lock it down:

```bash
# Edit sshd config
sudo nano /etc/ssh/sshd_config
```

Make sure these settings are active:

```
# Disable root login
PermitRootLogin no

# Use key-based auth only
PasswordAuthentication no
PubkeyAuthentication yes

# Use a non-standard port (optional but reduces noise)
Port 2222

# Limit login attempts
MaxAuthTries 3
MaxSessions 2

# Disable X11 forwarding (don't need it)
X11Forwarding no
```

After saving:

```bash
sudo systemctl restart sshd
```

> ⚠️ **Before closing your current SSH session**, open a **second terminal** and test that you can still log in. A misconfigured SSH can lock you out!

## 8.5 Fail2Ban — Auto-Block Brute Force Attacks

Fail2Ban monitors auth logs and temporarily bans IPs with too many failed attempts.

```bash
# Install
sudo apt install fail2ban -y

# Create a local config
sudo tee /etc/fail2ban/jail.local << 'EOF'
[DEFAULT]
bantime = 3600
findtime = 600
maxretry = 5

[sshd]
enabled = true
port = ssh
logpath = %(sshd_log)s
maxretry = 3
bantime = 86400
EOF

# Start it
sudo systemctl enable --now fail2ban
```

Check ban status:

```bash
sudo fail2ban-client status sshd
```

## 8.6 Secrets Management (Advanced)

For production setups, consider a real secrets manager:

### Option A: systemd-creds (built-in, no extra deps)

```bash
# Encrypt a credential
systemd-creds encrypt --name=openrouter_key - ~/.credentials/openrouter.cred

# Reference it in the service file
# EnvironmentFile=-/run/credentials/hermes.service
# ... then load from the encrypted file at boot
```

### Option B: Use a .env file with restricted permissions

```bash
# Create an env file
touch /home/agentuser/.hermes/.env
chmod 600 /home/agentuser/.hermes/.env
chown agentuser:agentuser /home/agentuser/.hermes/.env

# Edit it
nano /home/agentuser/.hermes/.env
# Add:
# OPENROUTER_API_KEY=sk-or-v1-...
# GEMINI_API_KEY=AIzaSy-...
```

Then modify your systemd service to load the env file:

```bash
sudo mkdir -p /etc/systemd/system/hermes.service.d

sudo tee /etc/systemd/system/hermes.service.d/envfile.conf << 'EOF'
[Service]
EnvironmentFile=/home/agentuser/.hermes/.env
EOF
```

## 8.7 Firewall: UFW

A simple firewall prevents unexpected services from being exposed:

```bash
# Install UFW
sudo apt install ufw -y

# Default deny incoming
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Allow SSH (change port if you changed it)
sudo ufw allow ssh

# Allow Hermes webhook port (if you use webhooks)
sudo ufw allow 8080/tcp

# Enable
sudo ufw enable

# Check status
sudo ufw status verbose
```

## 8.8 Hermes-Specific Security

### Restrict file access

By default, Hermes can read any file the user can read. Limit this:

```yaml
# In config.yaml
file_access:
  allowed_paths:
    - /home/agentuser/hermes-guide/
    - /home/agentuser/.hermes/
  denied_paths:
    - /etc/shadow
    - /root/
    - /home/agentuser/.ssh/
```

> **Note:** Check if your version of Hermes supports `file_access` restrictions. If not, OS-level permissions are your next best bet.

### Limit terminal commands

For safety-critical servers, restrict what commands Hermes can run:

```yaml
# In config.yaml
terminal:
  allowed_commands:
    - "ls"
    - "cat"
    - "python*"
    - "git"
    - "docker*"
    - "hermes*"
  denied_commands:
    - "rm -rf /"
    - "shutdown"
    - "reboot"
    - "su"
    - "sudo"
```

### Monitor usage

Set up a simple monitor to detect unusual activity:

```bash
# Create a simple watchdog script
cat > /home/agentuser/watchdog.sh << 'EOF'
#!/bin/bash
# Check Hermes is running, alert if down
if ! systemctl is-active --quiet hermes.service; then
    echo "Hermes is DOWN as of $(date)" >> /home/agentuser/hermes-alerts.log
    # Optional: send yourself a notification
    # curl -s "https://api.telegram.org/bot<TOKEN>/sendMessage?chat_id=<ID>&text=Hermes+is+down"
fi
EOF

chmod +x /home/agentuser/watchdog.sh

# Add to cron (check every 5 minutes)
crontab -e
# Add: */5 * * * * /home/agentuser/watchdog.sh
```

## 8.9 Regular Updates

| Component | Update Frequency | Command |
|---|---|---|
| Hermes Agent | Monthly | `hermes update` or re-run the install script |
| System packages | Weekly | `sudo apt update && sudo apt upgrade -y` |
| systemd service | After config changes | `sudo systemctl daemon-reload && sudo systemctl restart hermes` |
| AI models (skills) | As needed | `hermes skills update` |

### Automate system updates

```bash
# Install unattended-upgrades
sudo apt install unattended-upgrades -y
sudo dpkg-reconfigure -plow unattended-upgrades
```

## 8.10 Security Checklist

Use this checklist to verify your setup:

```
☐ Hermes runs as a non-root dedicated user
☐ No passwordless sudo for the Hermes user
☐ SSH key-only auth, no password login
☐ Root SSH login disabled
☐ fail2ban installed and active
☐ UFW firewall enabled (SSH + webhook ports only)
☐ API keys stored via environment variables, not in config.yaml directly
☐ API keys have usage limits/restrictions at provider level
☐ .env file permissions set to 600 (owner-only readable)
☐ systemd service configured with limited user
☐ Hermes logs monitored (journalctl check weekly)
☐ System auto-updates enabled (unattended-upgrades)
☐ Server backups configured (at minimum: ~/.hermes/config.yaml + skills)
```

---

**Chapter Summary:**
- ✅ Run Hermes as a non-root user — this is non-negotiable
- ✅ Store API keys in environment variables, not in config.yaml
- ✅ Harden SSH: disable passwords, disable root login
- ✅ Add fail2ban to block brute-force attacks
- ✅ Set up UFW firewall — only expose what's needed
- ✅ Restrict Hermes's file access and terminal commands
- ✅ Set up a watchdog to monitor Hermes uptime
- ✅ Keep everything updated: Hermes, system packages, firewall rules

**Next up:** Chapter 9 — Automation Recipes

---

# Chapter 9: Automation Recipes — 10 Copy-Paste Ready Workflows

> **"The best part of running your own AI agent: automate anything. Here are 10 recipes you can deploy today."**

Each recipe in this chapter follows the same format: what it does, how to set it up, and the exact commands to run.

## Recipe 1: Daily News Briefing → WeChat Every Morning

**What it does:** Sends a 3-item news summary + weather to your phone at 7 AM.

**Step 1:** Save the skill (from Chapter 7 — create `daily-briefing` skill first).

**Step 2:** Create a cron job:

```bash
hermes cron create "0 7 * * *" \
  --name "morning-briefing" \
  --prompt "Run the daily-briefing skill and send the result to WeChat" \
  --skills daily-briefing
```

**Verify:**
```bash
hermes cron list
```

> **Pro tip:** Run it once manually to test before the 7 AM trigger:
> ```bash
> hermes cron run <job-id>
> ```

## Recipe 2: Website Change Detector

**What it does:** Checks a website daily and alerts you if content changed.

Create a skill called `site-watcher` that does:

1. Fetch the page content
2. Compare with a saved hash
3. If different → notify + update the hash

Set it up:

```bash
hermes cron create "0 9 * * *" \
  --name "site-watcher" \
  --prompt "Check https://example.com/pricing for changes. Fetch the page, compare with ~/site-hash.txt, if different send me an alert on WeChat with what changed, then update the hash."
```

## Recipe 3: Stock/Price Alert (Custom)

**What it does:** Checks a specific stock or product price on schedule.

```bash
hermes cron create "0 */4 * * *" \
  --name "price-watch-AAPL" \
  --prompt "Check the current price of AAPL stock. If it dropped more than 3% since yesterday's close, send me an alert on WeChat with the price and percentage change."
```

For a product on Amazon, replace the prompt with:

```
"Check the price of [product URL]. If it's below $50, send me an alert with the price and link."
```

## Recipe 4: Server Health Report

**What it does:** Emails or messages you a server health check every morning.

```bash
hermes cron create "0 6 * * *" \
  --name "server-health" \
  --prompt "Check the server health: run 'df -h' for disk, 'free -h' for memory, 'uptime' for system load, 'ps aux | wc -l' for processes. Format as a brief health report and send to WeChat. If any metric is critical (disk > 90%, memory < 500MB), use ALL CAPS to flag it."
```

## Recipe 5: RSS Feed → AI Summary → Chat

**What it does:** Monitors an RSS/Atom feed and sends you AI-summarized updates.

```bash
hermes cron create "0 8,18 * * *" \
  --name "rss-watcher" \
  --prompt "Fetch and parse this RSS feed: https://hnrss.org/frontpage. For the top 5 stories, write a one-sentence summary of each. Send the summaries to WeChat with links."
```

## Recipe 6: Email Auto-Summarizer

**What it does:** Summarizes your unread emails and flags urgent ones.

> **Requires:** Email integration via Hermes Gateway

```bash
hermes cron create "0 9,14 * * 1-5" \
  --name "email-summary" \
  --prompt "Check my email inbox. Find the 5 most important unread emails. Summarize each: sender, subject, and key point. Flag any that mention 'urgent', 'deadline', or 'overdue' with ⚠️. Send to WeChat."
```

## Recipe 7: GitHub Repository Watcher

**What it does:** Checks your starred repos for new releases/issues.

```bash
hermes cron create "0 10 * * 1" \
  --name "github-watch" \
  --prompt "Check the GitHub repo NousResearch/hermes-agent for: (1) new releases in the last week, (2) open issues tagged 'good first issue'. Summarize and send to WeChat."
```

## Recipe 8: Language Learning Flashcards

**What it does:** Sends you daily vocabulary in your target language.

```bash
hermes cron create "0 20 * * *" \
  --name "japanese-vocab" \
  --prompt "Generate 5 Japanese vocabulary words for a beginner. Format each as: word (in Japanese), reading (hiragana), English meaning, example sentence. Send to WeChat as a flashcard-style message."
```

Change "Japanese" to your target language and "beginner" to your level.

## Recipe 9: Weekly Research Report

**What it does:** Researches a topic and saves a report every Sunday.

```bash
hermes cron create "0 9 * * 0" \
  --name "weekly-research" \
  --prompt "Research the latest developments in [your field/interest]. Search for 5 recent articles or papers. For each, write: (1) what it is, (2) why it matters, (3) key takeaway. Save the report to ~/research/weekly-report-$(date +%Y-%m-%d).md and send a summary to WeChat."
```

## Recipe 10: Custom Research Agent

**What it does:** Takes a topic, produces a structured markdown report.

This works as a skill rather than a cron job. Create `~/.hermes/skills/deep-research/SKILL.md`:

```markdown
---
name: deep-research
description: Given a topic, produces a structured research report
tags: [research, report, analysis]
---

# Deep Research Skill

## How to use
Say: "Research [topic] and write a report"

## Steps

1. Search the web for the topic (3-5 different searches from different angles)
2. Read and extract key information from each source
3. Organize into sections:
   - Overview (2-3 paragraphs)
   - Key Findings (bullet points)
   - Notable Details
   - Contrarian Views or Debates
   - Sources (with links)
4. Write to `~/research/<topic-slug>-<date>.md`
5. Summarize the report to the user
```

Usage: `/skill deep-research` then *"Research serverless AI inference options in 2025."*

## Cron Job Management Cheat Sheet

```bash
hermes cron list                              # List all jobs
hermes cron run <job-id>                      # Run job immediately
hermes cron pause <job-id>                    # Pause a job
hermes cron resume <job-id>                   # Resume a paused job
hermes cron remove <job-id>                   # Delete a job

# Schedule formats:
hermes cron create "0 7 * * *" ...            # Every day at 7 AM
hermes cron create "*/30 * * * *" ...         # Every 30 minutes
hermes cron create "0 9 * * 1" ...            # Every Monday at 9 AM
hermes cron create "2025-06-01T09:00:00" ...  # One-time on June 1
hermes cron create "30m" ...                  # Every 30 minutes (simple)
hermes cron create "every 2h" ...             # Every 2 hours (simple)
```

---

**10 recipes. Zero ongoing effort.** Set them up once, and your agent does the work forever.

**Chapter 11** covers troubleshooting — the real-world problems you'll encounter and exactly how to fix them.

---

# Chapter 10: Config.yaml Deep Dive

> **"Every line in your config file explained — so you can tune Hermes like a pro."**

The `config.yaml` file is the heart of your Hermes Agent. It controls everything: which AI providers to use, which platforms to connect to, how memory works, what cron jobs run, and more.

By the end of this chapter, you'll understand every field in the config and know exactly what to tweak.

## 10.1 Where Is the Config File?

```bash
# Default location
~/.hermes/config.yaml

# Or check with
hermes config path
```

If you don't have one yet, create it:

```bash
hermes config init
```

This generates a default config with sensible defaults. Throughout this chapter, we'll customize it section by section.

## 10.2 Complete Config Reference

Here's a full annotated config with every option explained:

```yaml
# ═══════════════════════════════════════════
# HERMES AGENT — COMPLETE CONFIGURATION
# ═══════════════════════════════════════════

# ── Main Provider ──────────────────────────
# The primary AI model Hermes uses for conversations.
provider: openrouter                        # Provider name
model: openrouter/anthropic/claude-sonnet-4 # Full model identifier
#                                           # Common values:
#                                           #   openrouter -> openrouter/anthropic/claude-sonnet-4
#                                           #   gemini     -> gemini/gemini-2.5-flash
#                                           #   openai     -> openai/gpt-4o
#                                           #   custom     -> (your own endpoint)

# ── Providers ──────────────────────────────
# API keys and settings for each provider.
providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"        # Use env vars for security!
    # base_url: https://openrouter.ai/api/v1 # Optional: override API endpoint

  gemini:
    api_key: "${GEMINI_API_KEY}"

  openai:
    api_key: "${OPENAI_API_KEY}"
    # organization: org-xxx                 # Optional: OpenAI org ID
    # project: proj_xxx                     # Optional: OpenAI project ID

  anthropic:
    api_key: "${ANTHROPIC_API_KEY}"

  custom:
    api_key: "${CUSTOM_API_KEY}"
    base_url: "https://your-endpoint.com/v1" # Required for custom providers
    # default_model: "your-model-name"       # Default model for this provider

# ── Skills ─────────────────────────────────
# Skills are reusable abilities Hermes can load.
skills:
  enabled: true                             # Master switch for skills
  # auto_load:                              # Skills to always load on startup
  #   - web-search
  #   - github
  # paths:                                  # Additional skill directories
  #   - /home/agentuser/my-custom-skills

# ── Memory ─────────────────────────────────
# How Hermes remembers information between sessions.
memory:
  # max_entries: 10                         # Max memory entries per store
  # max_chars: 2200                         # Max characters per memory store
  # stores:                                 # Additional memory stores
  #   - user-preferences
  #   - project-context

# ── Tools ──────────────────────────────────
# Which capabilities Hermes can use.
tools:
  enabled:
    - terminal                              # Run shell commands
    - file                                  # Read/write files
    - web_search                            # Search the internet
    - memory                                # Save/recall information
    - skills                                # Load/manage skills
    - cronjob                               # Schedule automated tasks
  # disabled:                               # Tools to explicitly block
  #   - docker

# ── Terminal (Shell Access) ────────────────
# Controls for Hermes's shell access.
terminal:
  # allowed_commands:                       # Limit to specific commands
  #   - "python*"
  #   - "git"
  # workdir: /home/agentuser                # Default working directory
  # timeout: 180                            # Max seconds for any command (default: 180)
  # background_timeout: 3600                # Max seconds for background processes

# ── File Access ────────────────────────────
# Controls which files Hermes can read/write.
file:
  # allowed_paths:                          # Restrict file access to these dirs
  #   - /home/agentuser
  # denied_paths:                           # Always block these files
  #   - /etc/shadow
  #   - /home/agentuser/.ssh/

# ── Platforms / Channels ───────────────────
# Where Hermes lives and how you talk to it.
platforms:
  # ── Console / CLI ──
  console:
    enabled: true                           # CLI mode (running `hermes` in terminal)
    # theme: default                        # UI theme for TUI mode

  # ── WeChat ──
  weixin:
    enabled: false                          # Set to true after WeChat setup
    # app_id: wx_xxxxxxxxxxxxx
    # app_secret: "${WECHAT_APP_SECRET}"
    # token: your_wechat_token

  # ── Telegram ──
  telegram:
    enabled: false
    # bot_token: "${TELEGRAM_BOT_TOKEN}"
    # allowed_chat_ids:                     # Restrict who can message the bot
    #   - 123456789

  # ── Discord ──
  discord:
    enabled: false
    # bot_token: "${DISCORD_BOT_TOKEN}"
    # guild_id: "123456789"

  # ── Slack ──
  slack:
    enabled: false
    # bot_token: "${SLACK_BOT_TOKEN}"
    # signing_secret: "${SLACK_SIGNING_SECRET}"

# ── Voice ──────────────────────────────────
# Text-to-speech settings for voice responses.
voice:
  # provider: elevenlabs                    # elevenlabs, openai, etc.
  # voice_id: your_voice_id
  # language: en-US

# ── Cron Jobs ──────────────────────────────
# Scheduled tasks that run automatically.
cron:
  # max_concurrent: 3                       # Max parallel cron executions
  # max_history: 100                        # How many past runs to keep
  # ── Example job ──
  # jobs:
  #   morning_briefing:
  #     schedule: "0 8 * * *"              # Every day at 8 AM
  #     prompt: "Give me a daily briefing: news headlines, weather, and my schedule."
  #     deliver: telegram                   # Send to Telegram
  #     enabled: true

# ── Webhook / Gateway ──────────────────────
# Optional HTTP server for webhook-based communication.
gateway:
  # enabled: false
  # host: 0.0.0.0                          # Listen address
  # port: 8080                             # Listen port
  # secret: "${GATEWAY_SECRET}"            # Auth secret for webhook calls

# ── Logging ────────────────────────────────
logging:
  # level: info                            # debug, info, warn, error
  # format: text                           # text or json
  # file: /home/agentuser/.hermes/hermes.log

# ── Advanced ───────────────────────────────
advanced:
  # max_tool_calls_per_turn: 50            # Max tool calls before requiring user input
  # max_context_tokens: 64000              # Max tokens for conversation context
  # session_search_enabled: true           # Enable cross-session search
  # update_check: true                     # Check for updates on startup
```

## 10.3 Core Configs Explained

### Provider Choice — Which Model Should You Use?

| Model | Cost | Speed | Quality | Best For |
|---|---|---|---|---|
| Claude Sonnet 4 (OpenRouter) | ~$3/M tokens | ⚡ Fast | ⭐⭐⭐⭐⭐ | Default all-purpose |
| Gemini 2.5 Flash (free tier) | Free* | ⚡ Very fast | ⭐⭐⭐⭐ | Testing, daily tasks |
| GPT-4o (OpenAI) | ~$5/M tokens | ⚡ Fast | ⭐⭐⭐⭐⭐ | Complex reasoning |
| DeepSeek Chat (OpenRouter) | ~$0.5/M tokens | ⚡ Fast | ⭐⭐⭐⭐ | Budget-friendly |
| OpenRouter Claude Opus 4 | ~$15/M tokens | 🐢 Slower | ⭐⭐⭐⭐⭐ | Maximum quality |

> *Gemini free tier: 60 requests/minute, 1,500 requests/day limit.

### Switching Providers

To change your active model, update the top-level `provider` and `model` fields:

```yaml
# Switch to Gemini (free tier)
provider: gemini
model: gemini/gemini-2.5-flash
```

Different providers use different model name formats. Here's a quick reference:

| Provider | Config Format | Example |
|---|---|---|
| OpenRouter | `openrouter/VENDOR/MODEL` | `openrouter/anthropic/claude-sonnet-4` |
| Gemini | `gemini/MODEL` | `gemini/gemini-2.5-flash` |
| OpenAI | `openai/MODEL` | `openai/gpt-4o` |
| Anthropic | `anthropic/MODEL` | `anthropic/claude-sonnet-4-20250514` |
| Custom | Depends on your endpoint | `custom/gpt-4o-mini` |

## 10.4 Platform Configuration Deep Dive

### WeChat Connection

Setting up WeChat requires a WeChat Official Account (订阅号 or 服务号). See Chapter 4 for the full setup, but the config fields are:

```yaml
platforms:
  weixin:
    enabled: true
    app_id: wx_xxxxxxxxxxxxx                # From WeChat Official Account admin
    app_secret: "${WECHAT_APP_SECRET}"      # Keep this in env vars!
    token: your_custom_token                # Any string you choose (used for verification)
```

### Telegram Bot Setup

```yaml
platforms:
  telegram:
    enabled: true
    bot_token: "${TELEGRAM_BOT_TOKEN}"      # From @BotFather on Telegram
    allowed_chat_ids:                       # Security: only allow specific chats
      - 123456789                           # Your Telegram user ID
```

To find your Telegram chat ID:

```bash
# Message your bot, then run:
curl -s "https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates" | jq '.result[0].message.chat.id'
```

## 10.5 Cron Jobs Configuration

Scheduled tasks are defined directly in config.yaml:

```yaml
cron:
  jobs:
    morning_briefing:
      schedule: "0 8 * * *"               # Cron expression: 8 AM daily
      prompt: "Read https://news.ycombinator.com and give me a 3-bullet summary of the top 5 stories."
      deliver: weixin                      # Send to WeChat
      enabled: true

    server_health_check:
      schedule: "*/30 * * * *"            # Every 30 minutes
      prompt: "Run 'df -h', 'free -h', 'uptime', and report if disk > 80% or memory < 500MB free."
      deliver: telegram
      enabled: true

    weekly_price_check:
      schedule: "0 9 * * 1"               # Mondays at 9 AM
      prompt: "Check the current price of ETH and BTC, compare to last week, summarize."
      deliver: telegram
      enabled: true
```

### Cron Schedule Reference

```
 ┌───────── minute (0-59)
 │ ┌───────── hour (0-23)
 │ │ ┌───────── day of month (1-31)
 │ │ │ ┌───────── month (1-12)
 │ │ │ │ ┌───────── day of week (0-7, 0=Sun)
 │ │ │ │ │
 * * * * * command
```

Common patterns:

| Expression | Meaning |
|---|---|
| `0 8 * * *` | Daily at 8 AM |
| `*/30 * * * *` | Every 30 minutes |
| `0 9 * * 1` | Mondays at 9 AM |
| `0 0 1 * *` | 1st of every month |
| `0 7,18 * * *` | 7 AM and 6 PM daily |

## 10.6 Memory Configuration

Memory is what makes Hermes "know" you over time:

```yaml
memory:
  max_entries: 10                          # Max separate memory entries (default)
  max_chars: 2200                          # Total character limit for memory
```

When memory fills up, Hermes automatically consolidates old entries (removes duplicates, merges related info) — you don't need to manage it manually.

**Tip:** If you find Hermes forgetting things, increase `max_chars`:

```yaml
memory:
  max_chars: 5000                          # More memory = better recall
```

## 10.7 Tool Configuration

Control which capabilities Hermes can use:

```yaml
tools:
  enabled:
    - terminal                              # Shell access (keep enabled)
    - file                                  # File read/write
    - web_search                            # Internet search
    - memory                                # Persistent memory
    - skills                                # Skill system
    - cronjob                               # Scheduled tasks
  disabled: []
```

**Security tip:** If you only want a chat agent with no server access:

```yaml
tools:
  enabled:
    - memory
    - web_search
    - skills
  disabled:
    - terminal                              # Disable shell access
    - file                                  # Disable file access
```

## 10.8 Usage-Limited Configuration

You can switch between different configs for different use cases. Keep multiple config files:

```bash
# Create a "safe" config (no shell access)
cp ~/.hermes/config.yaml ~/.hermes/config.safe.yaml
# Edit to disable terminal + file tools

# Create a "full access" config
cp ~/.hermes/config.yaml ~/.hermes/config.full.yaml
# Keep everything enabled

# Run with a specific config
hermes --config ~/.hermes/config.safe.yaml
```

## 10.9 Config Validation

Before applying config changes, validate your YAML syntax:

```bash
# Basic YAML check (requires Python)
python3 -c "import yaml; yaml.safe_load(open('/home/agentuser/.hermes/config.yaml')); print('✅ Valid YAML')"

# Or use hermes itself
hermes config validate
```

## 10.10 Common Config Mistakes

### Mistake 1: Missing API Key

```yaml
# ❌ Wrong — missing key
providers:
  openrouter:
    model: openrouter/anthropic/claude-sonnet-4

# ✅ Correct
providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"
```

### Mistake 2: Wrong Indentation

YAML is indentation-sensitive. Use 2 spaces (not tabs):

```yaml
# ❌ Wrong — inconsistent indentation
platforms:
    telegram:        # ← 4 spaces (might work, but inconsistent)
  enabled: true      # ← 2 spaces

# ✅ Correct
platforms:
  telegram:          # ← 2 spaces
    enabled: true    # ← 4 spaces (consistent)
```

### Mistake 3: Forgetting Quotes

```yaml
# ❌ Wrong — YAML may interpret as number
telegram:
  chat_id: 0123456789    # Leading zero: parsed as octal!

# ✅ Correct — force string
telegram:
  chat_id: "0123456789"
```

### Mistake 4: Env Var Not Exported

```yaml
providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"
```

If `OPENROUTER_API_KEY` isn't set when you run `hermes`, you'll get an auth error:

```bash
# Check if it's set
echo $OPENROUTER_API_KEY

# If empty, add to ~/.bashrc and reload
echo 'export OPENROUTER_API_KEY="sk-or-v1-..."' >> ~/.bashrc
source ~/.bashrc
```

## 10.11 Sample Configs by Use Case

### 🧪 Minimal Testing Config

```yaml
provider: gemini
model: gemini/gemini-2.5-flash
providers:
  gemini:
    api_key: "${GEMINI_API_KEY}"

skills:
  enabled: true

tools:
  enabled: [terminal, file, memory, web_search, skills]

platforms:
  console:
    enabled: true
```

### 🏠 Personal Assistant (Full Setup)

```yaml
provider: openrouter
model: openrouter/anthropic/claude-sonnet-4

providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"
  gemini:
    api_key: "${GEMINI_API_KEY}"

skills:
  enabled: true

tools:
  enabled: [terminal, file, memory, web_search, skills, cronjob]

platforms:
  console:
    enabled: true
  weixin:
    enabled: true
    app_id: wx_xxxxxxxxxxxxx
    app_secret: "${WECHAT_APP_SECRET}"
    token: my_custom_token

cron:
  jobs:
    morning_briefing:
      schedule: "0 8 * * *"
      prompt: "Give me today's briefing: news, weather, and any server issues."
      deliver: weixin
      enabled: true
```

### 🔒 Secure (No Shell Access)

```yaml
provider: openrouter
model: openrouter/anthropic/claude-sonnet-4

providers:
  openrouter:
    api_key: "${OPENROUTER_API_KEY}"

skills:
  enabled: true

tools:
  enabled: [memory, web_search, skills]
  disabled: [terminal, file]

platforms:
  telegram:
    enabled: true
    bot_token: "${TELEGRAM_BOT_TOKEN}"
    allowed_chat_ids:
      - 123456789
```

---

**Chapter Summary:**
- ✅ `config.yaml` controls everything — providers, platforms, tools, cron jobs
- ✅ Store API keys as environment variables, never hardcode them
- ✅ YAML indentation matters: use 2 spaces consistently
- ✅ Validate config changes with `hermes config validate`
- ✅ Keep multiple config files for different use cases (safe vs full access)
- ✅ Cron jobs use standard cron expressions — common patterns provided
- ✅ Use the right config for your needs (minimal, personal assistant, or secure)

**Next up:** Chapter 11 — Troubleshooting Common Problems

---

# Chapter 11: Troubleshooting Common Problems

> **"Everything that can go wrong — and exactly how to fix it."**

This chapter collects real problems I encountered while running Hermes across two different servers. If something breaks, check here first.

## 11.1 Installation Problems

### "curl: command not found"

```bash
# Ubuntu/Debian
sudo apt update && sudo apt install curl -y

# CentOS/RHEL
sudo yum install curl -y
```

### "Permission denied" during install

Run as a user with sudo access, or:

```bash
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | sudo bash
```

### "hermes: command not found" after install

The installer updates `~/.bashrc` but your current session doesn't see it:

```bash
source ~/.bashrc
# OR
exec $SHELL -l
```

If it still doesn't work, check if the install actually ran:

```bash
ls -la ~/.hermes/
```

If the directory is empty or missing, re-run the install.

### Install hangs or is very slow

Some VPS providers have slow connections to GitHub. Try:

```bash
# First, update your system
sudo apt update && sudo apt install python3 python3-venv git -y

# Then manually clone and install
git clone https://github.com/NousResearch/hermes-agent.git ~/.hermes/hermes-agent
cd ~/.hermes/hermes-agent
python3 -m venv venv
source venv/bin/activate
pip install -e .
```

## 11.2 Model / Provider Issues

### "No models provided" or HTTP 400

This usually means the model name doesn't match what the provider expects.

**Fix:** Check the exact model name:

```bash
hermes config set model.default gemini-2.5-flash
```

Common correct names:
- Google: `gemini-2.5-flash`, `gemini-2.5-pro`
- OpenRouter: `openai/gpt-4o-mini`, `anthropic/claude-sonnet-4`
- OpenAI: `gpt-4o`, `gpt-4o-mini`
- Anthropic: `claude-sonnet-4`, `claude-haiku-4`

### "401 Unauthorized" or "Invalid API key"

Your `.env` file has a wrong or missing key.

```bash
# Check if the key exists
cat ~/.hermes/.env | grep API_KEY

# If it's there, check for typos
# If it's missing, add it
echo 'GOOGLE_API_KEY=AIza...your_key' >> ~/.hermes/.env

# Verify the config can read it
hermes doctor
```

### "Rate limit exceeded"

You hit the provider's rate limit. Solutions:

1. **Wait a minute** and try again
2. **Switch to a different model** temporarily
3. **Set up fallback models** (see Chapter 3.7)

### Provider works in web UI but not in Hermes

Some providers (like DeepSeek reasoning models) return extra fields (like `reasoning_content`) that Hermes doesn't handle. **Use the standard chat model version instead:**

```bash
# ❌ Don't use "deepseek-reasoner" (has thinking mode issues)
# ✅ Use "deepseek-chat" (standard chat, no problems)
hermes config set model.default deepseek-chat
```

## 11.3 Gateway Problems

### Gateway won't start

```bash
# Check logs
cat ~/.hermes/logs/gateway.log | tail -20

# Common fix: restart
hermes gateway restart

# If still failing, reset
systemctl --user reset-failed hermes-gateway
hermes gateway restart
```

### Gateway dies when I log out of SSH

Systemd user services don't survive logout by default:

```bash
sudo loginctl enable-linger $USER
```

This keeps the gateway running after you disconnect.

### WeChat not responding

Check:

```bash
# 1. Is the gateway running?
hermes gateway status

# 2. Is the platform configured?
hermes gateway setup

# 3. Is the webhook URL correct?
# Check in mp.weixin.qq.com → Settings → Basic Configuration
# URL should be: http://your-server-ip:9090/webhooks/weixin
```

### Telegram bot not responding

```bash
# 1. Is the bot token correct?
# Go to @BotFather on Telegram and /mybots → API Token

# 2. Is the gateway running?
hermes gateway status

# 3. Check gateway logs for errors
cat ~/.hermes/logs/gateway.log | grep -i error | tail -10
```

## 11.4 Cron Job Issues

### Cron job didn't run

```bash
# List jobs to confirm it's still there
hermes cron list

# Check if the scheduler is running
hermes gateway status

# Run it manually to test
hermes cron run <job-id>
```

### Cron job ran but no output received

The job ran but couldn't deliver. Check:

1. Is the Gateway running? (delivery needs the gateway)
2. Is the home channel set correctly?
3. Try: `hermes cron run <job-id> --deliver weixin`

### Cron job "Model not responding"

Your chosen provider was rate-limited or had an outage. Solutions:
- Add fallback models (Chapter 3.7)
- Use a different provider for cron jobs
- Schedule retries

## 11.5 General Errors

### Message too long

Hermes returns a very long response and it gets truncated on WeChat/Telegram.

**Fix:** Add to your prompt:
> "Be concise. Keep responses under 200 words."

Or set it in skills:
```yaml
# In your skill's instructions
- Keep all responses under 150 words
- Use bullet points, not paragraphs
```

### "Session not found"

```bash
hermes sessions list           # Find the session
hermes sessions browse         # Interactive picker
hermes --continue              # Resume most recent
```

### "Tool not available"

Some tools need to be enabled per-platform:

```bash
hermes tools                   # Interactive toggle
hermes tools enable web        # Enable web tool
hermes tools enable terminal   # Enable terminal tool
```

After changes, start a new session: `/reset`

### Memory not working

```bash
# Check memory status
hermes memory status

# Enable it
hermes config set memory.memory_enabled true

# Enable user profile
hermes config set memory.user_profile_enabled true
```

## 11.6 The Ultimate Reset

If nothing works, reset Hermes without losing your skills:

```bash
# 1. Save your API keys
cp ~/.hermes/.env ~/env-backup.txt

# 2. Back up skills
cp -r ~/.hermes/skills ~/skills-backup

# 3. Reinstall
hermes uninstall
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# 4. Restore
cp ~/env-backup.txt ~/.hermes/.env
cp -r ~/skills-backup/* ~/.hermes/skills/

# 5. Reconfigure
hermes setup
```

## Quick Reference: Error to Fix

| Error Message | Fix |
|--------------|------|
| `command not found: hermes` | `source ~/.bashrc` |
| `401 Unauthorized` | Check API key in `.env` |
| `HTTP 400` | Wrong model name |
| `Rate limit exceeded` | Wait or switch models |
| `Gateway not running` | `hermes gateway start` |
| `Cron job didn't deliver` | Check gateway status |
| `No models provided` | Check `model.default` in config |
| `session_search failed` | Check memory provider config |
| `Tool not available` | `hermes tools enable [name]` |

---

**That covers every major problem I've encountered.** If you hit something not listed here, run `hermes doctor` and check the logs — both will point you in the right direction.
