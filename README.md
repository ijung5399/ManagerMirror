# ManagerMirror

> A structured self-reflection framework for engineering managers navigating the hardest part of the job — people.

Managing systems is finite. Managing people is not. This project helps engineering managers work through real situations, surface blind spots, and build a personal management philosophy — one reflection at a time.

---

## Why This Exists

The transition from engineer to engineering manager is often described as a shift from solving technical problems to solving human ones. The tools are different. The feedback loops are slower. And unlike code, people don't behave predictably.

ManagerMirror is a harness for that process. It provides:
- A **knowledge base** of foundational frameworks (psychology, feedback, trust, leadership)
- A **structured format** for recording and reflecting on real situations
- A **coaching approach** that surfaces questions rather than prescribing answers
- A **Claude Code skill** (`/managermirror`) that guides sessions and saves results automatically

---

## How It Works

```
Real situation
      ↓
Coaching questions (one at a time, emotion first)
      ↓
Insight — what you couldn't see before
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

Create your personal folder:
```
users/
└── {your_username}/
    ├── profile/
    │   ├── self.md        # who you are as a manager (builds over time)
    │   └── triggers.md    # what sets you off and why
    ├── situations/        # one folder per session
    ├── principles/
    │   └── principles.md  # your accumulated principles
    └── log/               # raw session logs (optional)
```

Use `template/` as a reference for each file format.

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

## Claude Code Skill

If you use [Claude Code](https://claude.ai/code), a `/managermirror` skill is available.

It automatically:
- Loads the relevant foundations based on your situation
- Reads your accumulated profile, triggers, and principles
- Guides the session using coaching questions (one at a time, emotion first)
- Saves session outputs to the correct folder structure at the end

To install, place the `managermirror/` skill folder in your Claude skills directory.

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
