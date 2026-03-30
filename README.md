# Consulting Problem Solving

**A Claude Code skill that turns Claude into your consulting associate.**

Give it a messy business problem. Get back structured analysis, evidence-based recommendations, and presentation-ready deliverables — built through the same methodology used by top-tier strategy firms.

---

## How It Works

You play the **consulting partner** — the decision-maker with domain expertise.
Claude plays the **consulting associate** — bringing analytical frameworks, structured thinking, and execution.

Every step follows the same rhythm: you provide direction, Claude builds, you review and approve before moving forward. Nothing advances without your explicit sign-off.

### The 8-Step Process

```
 FRAME                    ANALYZE                   DELIVER
 ─────                    ───────                   ───────
 ┌─────────────┐         ┌─────────────┐          ┌─────────────┐
 │ 1. Define   │────────▶│ 5. Analyze  │─────────▶│ 7. Recommend│
 │    Problem   │         │             │          │             │
 └──────┬──────┘         └──────┬──────┘          └──────┬──────┘
        │                       │                        │
 ┌──────▼──────┐         ┌──────▼──────┐          ┌──────▼──────┐
 │ 2. Structure │         │ 6. Synthe-  │          │ 8. Communi- │
 │   (MECE)    │         │    size     │          │    cate     │
 └──────┬──────┘         └─────────────┘          └─────────────┘
        │                                          Slides or Docs
 ┌──────▼──────┐
 │ 3. Prioritize│
 └──────┬──────┘
        │
 ┌──────▼──────┐
 │ 4. Work Plan │
 └─────────────┘
```

| Step | What Happens | You Get |
|:----:|:-------------|:--------|
| **1** | Define the core question, scope, and success criteria | Problem statement (`.md`) |
| **2** | Decompose into a MECE issue tree with testable hypotheses | Issue tree (`.md` + `.svg`) |
| **3** | Rank branches by impact and feasibility | Priority matrix (`.md`) |
| **4** | Map analyses to questions, data sources, and dependencies | Work plan (`.xlsx`) |
| **5** | Execute each analysis, test hypotheses, track sources | Analysis workbook (`.xlsx`) + findings (`.md`) |
| **6** | Weave findings into a coherent answer (not just a summary) | Synthesis document (`.md`) |
| **7** | Build phased, evidence-backed recommendations with impact sizing | Recommendation brief (`.md`) |
| **8** | Shape the narrative and produce presentation-ready content | Slide content or document content (`.md`) |

You can run the full process end-to-end, or invoke any single step on its own.

---

## What Makes This Different

**You stay in control.** Claude doesn't disappear into a black box and return a 40-page deck. At every step, you provide input, review the output, and approve before anything moves forward. Your domain knowledge shapes every deliverable.

**Synthesis, not summary.** Step 6 doesn't just list findings — it weaves them into a coherent argument. "Here's what it all *means together*" is fundamentally different from "here's what we found."

**Narrative-first, not data-first.** Arguments are built on insight and logic. Numbers emphasize points — they never construct them. Every slide must make sense with the numbers removed.

**Built-in skepticism.** Before any final deliverable is built, a sceptical review agent stress-tests your storyline for logical gaps, unsupported claims, data-dump tendencies, and vague recommendations. You accept or reject each proposed change.

**Full traceability.** YAML frontmatter links every recommendation back through insights, findings, analyses, branches, and the original key question. You can trace any conclusion to its evidence.

**Two output tracks.** Choose between a **slides track** (distilled, one-message-per-slide, scannable) or a **vertical document track** (narrative prose with full argument depth) — each with purpose-built content rules.

---

## Installation

### As a Claude Code Skill

```bash
# From your project directory
claude install-skill https://github.com/wudpeker/consulting-problem-solving
```

### Manual Installation

Clone into your Claude Code skills directory:

```bash
git clone https://github.com/wudpeker/consulting-problem-solving.git \
  ~/.claude/skills/consulting-problem-solving
```

---

## Usage

Start a conversation with Claude Code and trigger the skill naturally:

> "Help me think through our market entry strategy for Southeast Asia"

> "I need a structured approach to figure out why customer retention is dropping"

> "Build me a recommendation deck for the board on whether we should acquire TargetCo"

Or invoke it directly:

> `/consulting-problem-solving`

Claude will set up an engagement folder, walk you through each step, and produce deliverables along the way.

### Trigger Phrases

The skill activates when you mention: *strategy consulting, problem solving framework, issue tree, MECE, hypothesis-driven, pyramid principle, 80/20 analysis, root cause analysis, business case analysis, strategic recommendation, structured thinking* — or simply ask for help systematically breaking down a complex problem.

---

## Example Workflow

**You:** "We're losing enterprise customers to a competitor that launched 6 months ago. Help me figure out what's going on and what to do about it."

**Step 1** — Claude asks about context, scope, and what success looks like. Produces a problem definition anchored to a precise key question.

**Step 2** — You choose a decomposition framework (or Claude suggests one). The problem splits into a MECE issue tree — e.g., *Product gaps vs. Pricing vs. Sales execution vs. Competitor strengths*.

**Step 3** — Together you assess which branches have the highest impact and are most feasible to investigate. Two or three become P1 focus areas.

**Step 4** — Claude builds a work plan: 15-20 specific analyses, each tied to a question, an approach, and a data source.

**Step 5** — Analyses run. Each finding gets a "so what?" test and a confidence level. Hypotheses are confirmed, partially confirmed, or disproven.

**Step 6** — Findings are synthesized into a coherent narrative — not a list, but an argument.

**Step 7** — Phased recommendations with impact sizing, implementation roadmaps, and risk mitigations.

**Step 8** — You choose slides or a document. Claude builds a storyline, runs the sceptical review, and produces presentation-ready content that a downstream builder skill (like `pptx` or `docx`) can render into a polished deliverable.

---

## Principles

| Principle | What It Means |
|:----------|:-------------|
| **User leads, Claude executes** | You have the domain knowledge and accountability. Claude has the frameworks and analytical rigor. |
| **MECE at every level** | Mutually Exclusive, Collectively Exhaustive. No overlaps, no gaps. Validated explicitly. |
| **Hypothesis-driven** | Form hypotheses early, test them in analysis, pivot when evidence says so. |
| **"So what?" relentlessly** | Every finding, every slide, every paragraph must answer: what does this mean for the decision? |
| **80/20 ruthlessly** | Focus on the 20% of issues driving 80% of impact. If you have more than 3-4 P1 items, you haven't prioritized. |
| **Data integrity** | Fewer high-confidence figures beat many loosely sourced ones. Every number gets a source. |
| **Consulting-grade prose** | Strunk & White integrated at every step. Active voice, definite language, omit needless words. |

---

## Repository Structure

```
consulting-problem-solving/
├── SKILL.md                              # Main skill definition and orchestration
└── references/
    ├── 01-define-problem.md              # Step 1: Problem definition guide
    ├── 02-structure-problem.md           # Step 2: MECE decomposition guide
    ├── 03-prioritize.md                  # Step 3: Impact/feasibility prioritization
    ├── 04-work-plan.md                   # Step 4: Analysis work plan structure
    ├── 05-analyze.md                     # Step 5: Analysis execution and data quality
    ├── 06-synthesize.md                  # Step 6: Synthesis methodology
    ├── 07-recommend.md                   # Step 7: Recommendation development
    ├── 08-communicate.md                 # Step 8: Communication orchestrator
    ├── 08-slides-content.md              # Step 8: Slides track content rules
    ├── 08-slide-content-format.md        # Step 8: Slide content spec format
    ├── 08-vertical-content.md            # Step 8: Vertical document content rules
    └── writing-style.md                  # Strunk & White consulting prose standards
```

---

## Integration with Other Skills

This skill owns **content and structure**. It does not produce visual output. After Step 8, hand the approved content to a builder skill for rendering:

- **Slides** &rarr; `pptx`, `html-landing-page`, or similar deck builder
- **Documents** &rarr; `docx`, `pdf`, or similar document builder
- **Styling** &rarr; `theme-factory` or `brand-guidelines` for visual identity

---

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI, desktop app, or IDE extension
- Claude model with tool use capability (Opus, Sonnet, or Haiku)

---

## License

MIT
