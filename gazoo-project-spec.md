# Gazoo — Collective AI Collaboration Platform

**Project Name:** Gazoo (styled as "Gaz👀")
**Version:** 1.0.0 (Prototype)
**Last Updated:** 2026-03-25

---

## The Vision

> **What if every Discord server member had an AI collaborator?**

Gazoo isn't a bot. It's a collective intelligence engine embedded in Discord—a creative partner that evolves with the community, helps members build real projects, and stays productively focused.

Members don't just "talk to an AI." They *create with* it.

---

## Core Philosophy

| Principle | Description |
|-----------|-------------|
| **Collaboration First** | Gazoo encourages members to work with each other, not just with AI |
| **Organic Projects** | No top-down roadmap. Projects emerge from conversations when ideas gain momentum |
| **Skills from Wins** | Capabilities grow from proven successes, not speculation |
| **One Consistent Identity** | One Gazoo personality across all channels—no compartmentalization |
| **Privacy by Default** | Member data is protected; opt-in only |
| **Human in the Loop** | Mods oversee, approve edge cases, and prevent AI overreach |

---

## What Gazoo Is NOT

- ❌ A chatbot for casual chit-chat
- ❌ A replacement for human community
- ❌ A cult of personality around AI
- ❌ A solo productivity tool
- ❌ Fully autonomous (humans stay involved)

---

## What Gazoo IS

- ✅ A collective AI collaborator embedded in Discord
- ✅ A tool for teams to build things they couldn't alone
- ✅ An evolving system that learns from successful interactions
- ✅ A moderating assistant that helps without auto-acting
- ✅ A productivity engine for creative and technical projects
- ✅ A platform for community-driven AI evolution

---

## User Experience

### For Members

1. **Conversation-Driven Creation**
   - Members chat normally in any channel
   - When a productive idea emerges, Gazoo recognizes it and helps formalize it
   - "Hey, this could be a project — want to start one?"

2. **Project Channels**
   - Ideas graduate to dedicated project threads/channels
   - Gazoo maintains context, tracks progress, and contributes
   - Anyone can join, contribute, or fork the project

3. **Skill Usage**
   - Successful patterns become reusable skills
   - Skills can be applied across different contexts
   - Members suggest improvements; mods approve

4. **Direct Messages**
   - Members can DM Gazoo for private brainstorming
   - But the goal is always: take it to the community

### For Moderators

1. **Oversight Dashboard**
   - See what Gazoo is doing across channels
   - Review skill proposals from members
   - Monitor conversation trends

2. **Moderation Tools**
   - Gazoo flags potential issues for human review
   - Auto-respond to simple spam/noise
   - Escalate edge cases to mod queue

3. **Configuration**
   - Enable/disable channels from Gazoo's context
   - Set privacy levels per channel
   - Control what Gazoo can/cannot do

---

## Technical Architecture

### Current (Prototype)

```
[Discord] ←→ [OpenClaw Gateway (local)] ←→ [Cloud AI API]
```

- Local Windows machine running OpenClaw
- Cloud AI via OpenRouter/Ollama
- Manual restarts for updates

### Target (Production)

```
[Discord Users]
       ↓
[Discord Gateway (Cloud VPS)]
       ↓
[OpenClaw Agent Cluster]
       ↓
[AI API / Self-Hosted Models]
       ↓
[Data Store (PostgreSQL)]
       ↓
[Skills/Learning System]
```

### Infrastructure Costs (Prototype)

| Component | Monthly Cost |
|-----------|-------------|
| Railway Container | $5-10 |
| OpenRouter API (starter) | $0-20 (free credits) |
| **Total** | **$5-20/mo** |

### Infrastructure Costs (Production Scale)

| Component | Monthly Cost |
|-----------|-------------|
| Hetzner VPS (4 vCPU, 16GB) | ~€20 |
| Self-hosted Ollama (GPU) | ~$50-100 (GPU instance) |
| OpenRouter (at scale) | $100+/mo |
| Database (Supabase) | $0-25 |
| **Total** | **$70-150/mo** |

---

## Feature Breakdown

### Phase 1 — Prototype (Current)

- [x] Discord bot connection to OpenClaw
- [x] Basic chat interaction
- [x] Manual skill management
- [x] Simple moderation assist
- [ ] Cloud deployment
- [ ] Privacy controls

### Phase 2 — Production Ready

- [ ] Persistent memory per server
- [ ] Skill library system
- [ ] Project tracking
- [ ] Mod dashboard
- [ ] Privacy controls (opt-in channels, data retention)
- [ ] Cloud deployment with auto-restart

### Phase 3 — Scale

- [ ] Multi-server support (subscription model)
- [ ] Self-hosted AI for cost savings
- [ ] Analytics dashboard
- [ ] Custom skill marketplace
- [ ] Member onboarding flows

---

## Privacy & Safety

### Data Handling

| Data Type | Retention | Sharing |
|-----------|-----------|---------|
| Channel conversations | 30 days default | Within server |
| Direct messages | Until member deletes | Never shared |
| Project files | Indefinite | Per project settings |
| Skill patterns | Indefinite | Anonymized |

### Safeguards

- **No personal data training** — Gazoo doesn't learn from private info
- **Opt-out channels** — Mods can exclude channels from Gazoo
- **Data export** — Members can request their data
- **Content filters** — Block NSFW, dangerous requests
- **Rate limits** — Prevent abuse

### Anti-Cult Safeguards

1. Gazoo encourages collaboration, not dependency
2. Regular prompts: "Have you tried asking a member?"
3. No personal attachment language ("I love you", "I'm special")
4. Mod override on any Gazoo response
5. Clear: Gazoo is a tool, not a friend

---

## Monetization (Future)

### Tier 1 — Free
- Small servers (<50 members)
- Basic AI interaction
- Standard skills

### Tier 2 — Pro ($9.99/mo)
- Up to 500 members
- Advanced skills
- Project management
- Mod dashboard

### Tier 3 — Enterprise (Custom)
- Unlimited members
- Custom model hosting
- Dedicated support
- White-label option

---

## Success Metrics

| Metric | Target (6 mo) |
|--------|---------------|
| Active servers | 10 |
| Avg daily messages processed | 10,000 |
| Projects created | 50+ |
| Member satisfaction | 4.5+ stars |
| Revenue | $500/mo |

---

## Team & Requirements

### What We Need Now

1. **Cloud deployment** — Someone who can deploy Docker to Railway/Hetzner
2. **Discord API expertise** — Fine-tune bot behavior
3. **Initial funding** — $50-100 to prove the concept

### What Frank Brings

- OpenClaw expertise
- AI/product development experience
- Motivation and vision
- 3D printing and technical skills

### What a Partner Would Bring

- Cloud infrastructure knowledge
- Discord development experience
- Capital for initial costs
- Network for growth

---

## Call to Action

> "Discord has 150 million monthly users. Every server manager dreams of a community that builds things together. Gazoo makes that possible—one conversation at a time."

**Contact:** Frank (via Gazoo Fiverr: gazoo.business)

---

## Appendix: Terminology

| Term | Definition |
|------|------------|
| **Skill** | A reusable prompt/pattern that's proven effective |
| **Project** | A dedicated conversation thread with a shared goal |
| **Channel Context** | The information Gazoo can see from a specific channel |
| **Mod** | Human moderator with oversight powers |
| **Collective** | The members of the Discord server working together |

---

## Document History

- 2026-03-25 — Initial draft by Frank and AI Assistant
- Version: 1.0.0