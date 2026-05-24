# ManagerMirror

> 🇺🇸 English | [🇰🇷 한국어](README.ko.md)

> A structured coaching framework for anyone navigating the manager-engineer relationship — whether you're the one managing or the one being managed.

The hardest part of working in tech isn't the code. It's the people. This project helps you work through real situations, understand the other side's perspective, and build a personal philosophy — one reflection at a time.

Originally built for engineering managers. Now equally useful for engineers trying to understand their managers, navigate difficult dynamics, or process experiences like PIP, performance reviews, or unexpected conflicts.

---

## Why This Exists

The manager-engineer relationship is one of the most consequential — and least understood — dynamics in tech. From the manager's side: giving feedback, handling underperformance, building trust. From the engineer's side: navigating PIPs, understanding why a manager reacted the way they did, or learning how organizational power actually works.

Both sides often lack a structured space to process what happened and build genuine understanding of the other.

ManagerMirror provides:
- A **knowledge base** of foundational frameworks (psychology, feedback, trust, leadership)
- A **structured format** for recording and reflecting on real situations
- A **coaching approach** that uses the GROW model and surfaces questions rather than prescribing answers
- **Perspective-taking** — when you can't understand the other side, the skill helps you generate plausible hypotheses and explore them
- **AI tool integration** — works with Claude Code (`/managermirror`), GitHub Copilot, ChatGPT, Hermes (Ollama), or any AI that can read files

---

## How It Works

Sessions follow the **GROW model**, extended with a Perspective-Taking stage:

```
Real situation
      ↓
G — Goal: what do you want from this session?
      ↓
R — Reality: what is actually happening? (one question at a time)
      ↓
P — Perspective: what might the other side be thinking, feeling, fearing, needing?
      ↓
O — Options: what could you do differently?
      ↓
W — Will: what will you actually do?
      ↓
Principles — accumulated over time
```

Each session produces three files:
- `situation.md` — what happened, in facts
- `challenge.md` — the uncomfortable questions raised
- `insight.md` — what was realized, what changes next time

Patterns accumulate in `profile/`. Principles accumulate in `principles/`. Over time, the mirror gets sharper.

---

## Getting Started

```bash
git clone https://github.com/{your-username}/ManagerMirror.git
cd ManagerMirror
```

Then start a session with your AI tool of choice. See [Supported AI Tools](#supported-ai-tools) below.

Your personal folder (`users/{your_username}/`) is created automatically as sessions progress — no manual setup needed.

> Your `users/` folder is listed in `.gitignore` and will **never be committed**. Your data stays local.

---

## Project Structure

```
ManagerMirror/
├── .gitignore              # excludes users/
├── README.md
├── foundations/            # shared knowledge base (11 files)
│   ├── 01_human_is_not_a_system.md
│   ├── 02_basic_human_needs.md
│   ├── 03_psychological_safety.md
│   ├── 04_trust.md
│   ├── 05_radical_candor.md
│   ├── 06_nonviolent_communication.md
│   ├── 07_difficult_conversations.md
│   ├── 08_feedback.md
│   ├── 09_situational_leadership.md
│   ├── 10_engineering_manager_traps.md
│   └── 11_questioning_techniques.md
├── template/               # file format references
│   ├── situation.md
│   ├── challenge.md
│   ├── insight.md
│   └── principles.md
└── users/                  # gitignored — your data only
    └── {your_username}/
```

---

## Foundations Knowledge Base

The `foundations/` folder contains 11 reference documents that power the coaching sessions. Each covers a core framework relevant to people management:

| File | Topic |
|------|-------|
| `01` | Why people are not systems — the engineer's mental model trap |
| `02` | Self-determination theory — autonomy, competence, relatedness |
| `03` | Psychological safety — the single biggest predictor of team performance |
| `04` | The trust equation — why self-orientation destroys trust |
| `05` | Radical Candor — care personally, challenge directly |
| `06` | Nonviolent Communication — observation → feeling → need → request |
| `07` | Difficult conversations — the 3 layers every hard talk contains |
| `08` | Feedback — SBI model, timing, and how to receive it |
| `09` | Situational leadership — matching your style to the person's stage |
| `10` | Engineering manager traps — fix-it mode, clarity obsession, and more |
| `11` | Questioning techniques — how to draw out what people can't say yet |

---

## Supported AI Tools

ManagerMirror works with any AI that can read files. Full instructions are in [`AGENTS.md`](AGENTS.md).

| AI Tool | How to use |
|---------|-----------|
| **Claude Code** | Install `skill/SKILL.md` → type `/managermirror` |
| **GitHub Copilot** | Open project in VS Code → `@workspace` with `AGENTS.md` |
| **OpenAI Codex / ChatGPT** | Upload `AGENTS.md` + relevant foundations files |
| **Hermes (Ollama)** | Use `AGENTS.md` as system prompt |

### Claude Code (full automation)

```bash
# Copy skill to your Claude skills directory
cp -r skill/ {claude_skills_dir}/managermirror/
```

Then in any session:
```
/managermirror
```

The skill auto-discovers the project location and your username — no configuration needed.

### Other AI tools

See [`AGENTS.md`](AGENTS.md) for step-by-step instructions for each tool.

---

## Privacy Model

| What | Where | Committed? |
|------|-------|------------|
| Knowledge base | `foundations/` | ✅ Yes |
| Templates | `template/` | ✅ Yes |
| Your situations | `users/{you}/situations/` | ❌ No |
| Your profile | `users/{you}/profile/` | ❌ No |
| Your principles | `users/{you}/principles/` | ❌ No |

This means you can share the framework without sharing any of your personal data.

---

## License

MIT
