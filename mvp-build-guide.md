# Gazoo MVP — Step-by-Step Build Guide

## Quick Overview

| Phase | Duration | Total Cost |
|-------|----------|------------|
| **Phase 1:** Local Prototype | 1 week | $0 |
| **Phase 2:** Cloud Deployment | 1 week | $5-10 |
| **Phase 3:** First Users | 2 weeks | $20-40 |
| **Phase 4:** Polish & Launch | 2 weeks | $20-50 |
| **TOTAL** | **~6 weeks** | **$45-100** |

---

## Phase 1: Local Prototype (Week 1)

### Goal: Get Discord bot talking to OpenClaw locally

### Step 1.1: Fix Discord Connection

**Problem:** OpenClaw isn't reading the `DISCORD_BOT_TOKEN` env var.

**Fix (try one by one):**

```
Option A: Set in System Environment (User level)
[Environment]::SetEnvironmentVariable("DISCORD_BOT_TOKEN", "YOUR_TOKEN_HERE", "User")

Option B: Hardcode temporarily (less secure, but works)
openclaw config set channels.discord.token "YOUR_BOT_TOKEN_HERE"

Option C: Create .env file in openclaw folder
DISCORD_BOT_TOKEN=YOUR_BOT_TOKEN_HERE
```

**Cost:** $0

**Verification:**
```bash
openclaw gateway restart
openclaw logs | Select-String "discord"
# Should see: "subsystem": "channels/discord" or similar
```

---

### Step 1.2: Test Basic Interaction

**Test Commands:**
1. Send message in Discord server
2. Check OpenClaw responds
3. Verify it remembers context

**Cost:** $0

---

### Step 1.3: Create Skill Structure

Create folder: `gazoo/skills/`

```
gazoo/
  skills/
    research/
      SKILL.md
    moderation/
      SKILL.md
    projects/
      SKILL.md
```

**Each skill needs:**
- Name and description
- Trigger conditions
- System prompt
- Example responses

**Cost:** $0

---

### Step 1.4: Create Project Template

File: `gazoo/templates/project-thread.md`

```markdown
# Project: [Name]

**Started:** [Date]
**Founder:** [User]
**Status:** Active | Paused | Complete

## Description
[What this project aims to do]

## Goals
- [ ] Goal 1
- [ ] Goal 2

## Team
- @founder (lead)
- @contributor1
- @contributor2

## Progress
[Updates go here]

## Artifacts
- [Link to file 1]
- [Link to file 2]
```

**Cost:** $0

---

### Phase 1 Deliverables

- [ ] Discord bot connects (can see messages)
- [ ] Basic response works
- [ ] Skill folder structure exists
- [ ] Project template ready

**Phase 1 Cost:** $0

---

## Phase 2: Cloud Deployment (Week 2)

### Goal: Get Gazoo running on a cloud server

### Step 2.1: Choose Hosting

| Provider | Cost | Setup Difficulty |
|----------|------|------------------|
| **Railway** (recommended) | $5-10/mo | Easy |
| Hetzner | €4-6/mo | Medium |
| DigitalOcean | $4-12/mo | Easy |
| Fly.io | $0-5/mo | Medium |

**Recommendation:** Railway - Docker-native, easiest setup

**Cost:** $5-10 one-time setup

---

### Step 2.2: Deploy to Railway

```bash
# 1. Install Railway CLI
npm install -g @railway/cli

# 2. Login
railway login

# 3. Initialize project
railway init gazoo-mvp

# 4. Add variables in Railway dashboard:
# - DISCORD_BOT_TOKEN=your_token_here
# - OPENAI_API_KEY=your_key_here (or use OpenRouter)
# - OPENCLAW_ENV=production

# 5. Deploy
railway up
```

**Cost:** $5-10/mo once deployed

---

### Step 2.3: Connect AI API

**Option A: OpenRouter (Recommended for MVP)**

1. Go to https://openrouter.ai/
2. Create free account
3. Get API key (comes with free credits)
4. Add to Railway: `OPENROUTER_API_KEY=your_key`

**Cost:** $0-20/mo (free tier available)

**Option B: Anthropic/OpenAI**

1. Get API key
2. Add to Railway
3. Update OpenClaw config

**Cost:** $10-50/mo depending on usage

---

### Step 2.4: Configure Domain (Optional)

```
railway domain add gazoo.yourdomain.com
# Or use Railway's default: gazoo-mvp.railway.app
```

**Cost:** $0-12/yr (if you buy domain)

---

### Phase 2 Deliverables

- [ ] Cloud server running
- [ ] Discord bot connects to cloud
- [ ] AI API connected
- [ ] Public URL accessible

**Phase 2 Cost:** $5-10 (first month)

---

## Phase 3: First Users (Weeks 3-4)

### Goal: Get 10 servers using Gazoo

### Step 3.1: Create Invite Link

In your Discord server:
1. Server Settings → Invite Links
2. Create new link
3. Set permissions (Admin for now)
4. Share in communities

**Cost:** $0

---

### Step 3.2: Onboard First Servers

**Process for each new server:**

```
1. Owner invites Gazoo bot
2. Gazoo sends welcome message:
   "Hi! I'm Gazoo, your collective AI collaborator.
    Set up your first project channel with /gazoo setup"
3. Owner creates #gazoo-projects channel
4. Gazoo monitors and learns
```

---

### Step 3.3: Gather Feedback

| Week | Task |
|------|------|
| Week 3 | Get 5 servers onboarded |
| Week 4 | Gather feedback, fix issues |

**Cost:** $0 (time only)

---

### Step 3.4: Track Usage

Create simple spreadsheet:

| Server | Members | Messages/Day | Projects Started | Issues |
|--------|---------|--------------|------------------|--------|
| Server 1 | 45 | 120 | 2 | None |
| Server 2 | 200 | 500 | 5 | Slow responses |

**Cost:** $0

---

### Phase 3 Deliverables

- [ ] 10 active servers
- [ ] Usage tracking
- [ ] Bug list
- [ ] Feature requests

**Phase 3 Cost:** $15-30 (2 months hosting)

---

## Phase 4: Polish & Launch (Weeks 5-6)

### Goal: Ready for paid users

### Step 4.1: Fix Critical Issues

Priority order:

1. **Critical:** Bot crashes or doesn't respond
2. **High:** Memory resets between restarts
3. **Medium:** Slow responses (>10 seconds)
4. **Low:** UI/UX improvements

**Cost:** $0

---

### Step 4.2: Add Payment System

**Option A: Discord Role Gate**

1. Create "Pro Member" role
2. Bot only activates premium features for that role
3. Manual payment via PayPal (what Frank has)

**Cost:** $0

**Option B: Payment Links**

1. Create PayPal payment link: $9.99/mo
2. User pays, gets code
3. Redeem code for Pro role

**Cost:** $0 (PayPal is free for personal)

---

### Step 4.3: Launch Landing Page

File: `gazoo-landing/index.html`

```html
<h1>Gazoo — Collective AI for Discord</h1>
<p>Transform your server into a creation engine.</p>
<a href="DISCORD_INVITE_LINK">Add to Discord</a>
<p>$9.99/month — 7-day free trial</p>
```

**Cost:** $0 (static HTML on Railway)

---

### Step 4.4: Public Announcement

1. Post in Discord communities
2. Share on Twitter/X
3. Post in r/discordapp, r/DiscordBots
4. Share GitHub link

**Cost:** $0

---

### Phase 4 Deliverables

- [ ] Bug fixes complete
- [ ] Payment system working
- [ ] Landing page live
- [ ] Public launch

**Phase 4 Cost:** $20-50 (2-3 months hosting)

---

## Total MVP Cost Breakdown

### Minimum (No Paid Features Yet)

| Item | One-time | Monthly | Notes |
|------|----------|---------|-------|
| Railway (MVP) | - | $5 | 1GB RAM, 1 vCPU |
| OpenRouter (free tier) | - | $0 | ~10k free msgs |
| Domain (optional) | $12/yr | - | gazoo.ai |
| **Total** | **$0-12** | **$5** | |

### Recommended (Full Features)

| Item | One-time | Monthly | Notes |
|------|----------|---------|-------|
| Railway Pro | - | $10 | More resources |
| OpenRouter (paid) | - | $20 | Enough for 10 servers |
| Domain | $12/yr | - | Your brand |
| PayPal (free) | - | $0 | Payment processing |
| **Total** | **$12** | **$30** | |

### Investment Ask (What to Raise)

| Phase | Amount | Purpose |
|-------|--------|---------|
| Cloud Setup | $50 | 3 months hosting |
| Marketing | $100 | Outreach, ads |
| Buffer | $50 | Unexpected costs |
| **Total** | **$200** | MVP launch |

---

## Quick Start Checklist

### Day 1-2: Fix Local
- [ ] Get Discord bot connecting locally
- [ ] Test message → response

### Day 3-4: Cloud
- [ ] Deploy to Railway
- [ ] Get public URL

### Day 5-7: First Users
- [ ] Invite 5 servers
- [ ] Fix issues as they come

### Week 2: Launch
- [ ] Landing page
- [ ] Announce publicly

---

## What Happens If You Get Stuck

| Problem | Solution |
|---------|----------|
| Bot won't connect | Check env var, restart gateway |
| AI not responding | Check API key, switch to backup API |
| Too slow | Upgrade Railway plan or use smaller model |
| Memory loss | Add database for persistence |
| Can't afford | Use free tiers, self-host later |

---

## Next Action

**Right now:** Try Step 1.1 - fix the Discord bot connection.

Want me to help you with that right now?