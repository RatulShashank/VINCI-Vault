# VINCI — Personal Intelligence System

---

## What This Is

VINCI is a personal second brain architecture for researchers, quantitative analysts, and developers who accumulate knowledge across multiple domains over time. It is not a tool — it is a system of conventions, schemas, and workflows that turns any AI coding agent into a disciplined knowledge maintainer.

The system is built around one core insight from Andrej Karpathy's LLM wiki pattern: **knowledge should be compiled once and kept current, not re-derived from raw sources on every query.** VINCI extends this into a full research pipeline with gap detection, hypothesis generation, and experiment tracking.

---

## Architecture

VINCI runs three independent knowledge vaults, each with its own schema and agent instructions:

```
VINCI/
├── quant-research/     ← alpha generation engine (primary)
├── dev-knowledge/      ← coding decisions and technical patterns
└── personal/           ← goals, health, self-improvement
```

Each vault follows the same five-layer model:

```
Agent layer         Claude Code · OpenCode · any MCP-compatible agent
      ↓
Graph layer         Graphify — extracts connections across code, papers, images, video
      ↓
Wiki layer          LLM-maintained markdown — synthesized, cross-linked, persistent
      ↓
Session memory      claude-mem — context continuity across sessions
      ↓
Viewer layer        Obsidian — graph view, web clipper, Dataview queries
```

---

## Quant Research Vault — Full Structure

The primary vault is designed as a self-improving research engine for quantitative finance:

```
quant-research/
├── raw/
│   ├── papers/             ← PDFs, arxiv downloads
│   ├── articles/           ← web clips, practitioner writing
│   ├── notion-exports/     ← Notion page exports
│   └── assets/             ← figures and images
├── codes/
│   ├── final/              ← validated notebooks and scripts with outputs
│   └── iterations/         ← drafts and experiments (gitignored)
├── output-notes/           ← results from code execution (staging area)
├── gap-engine/
│   ├── gaps.md             ← detected knowledge gaps
│   ├── cluster-analysis.md ← community structure from graph
│   └── prompts.md          ← reusable gap and insight prompts
├── graphify-out/           ← graph.json, GRAPH_REPORT.md (auto-generated)
├── wiki/
│   ├── papers/             ← one summary page per source
│   ├── strategies/         ← strategy families
│   ├── methods/            ← statistical and ML methods
│   ├── concepts/           ← market microstructure, risk, factor theory
│   ├── authors/            ← researchers and their work
│   ├── contradictions/     ← conflicting claims across sources
│   ├── questions/          ← gap-driven research questions
│   ├── insights/           ← generated hypotheses
│   ├── experiments/        ← backtest records and validation
│   ├── index.md
│   ├── log.md
│   └── thesis.md           ← evolving beliefs, supported by evidence
├── CLAUDE.md               ← agent schema (Claude Code)
└── AGENTS.md               ← agent schema mirror (OpenCode, Codex)
```

---

## The Alpha Generation Loop

```
Raw sources → Graphify extraction → Gap detection → Research questions
     ↑                                                       ↓
thesis.md ← Experiment validation ← Hypothesis generation ← Insights
```

Every input must connect, challenge, or extend something already in the wiki. The gap engine mines the knowledge graph for disconnected clusters, weak coverage areas, contradictions, and thesis beliefs with no supporting experiments. These become research questions, which become hypotheses, which become experiments.

---

## Tool Stack

| Tool | Role | Install |
|---|---|---|
| [ai-second-brain-skills](https://github.com/NulightJens/ai-second-brain-skills) | Wiki scaffolding, ingest workflows, self-heal lint | `git clone` + symlink |
| [Graphify](https://github.com/safishamsi/graphify) | Graph extraction across code, papers, images, YouTube | `pip install graphifyy` |
| [claude-mem](https://github.com/thedotmack/claude-mem) | Session memory across agents | `npx claude-mem install` |
| [code-review-graph](https://github.com/tirth8205/code-review-graph) | Blast-radius analysis for codebases | `pip install code-review-graph` |
| [Obsidian](https://obsidian.md) | Wiki viewer, graph view, web clipper | obsidian.md |
| Claude Code | Primary agent | `npm install -g @anthropic-ai/claude-code` |
| OpenCode | Secondary agent | `npm install -g opencode-ai` |
| Git | Version history per vault | built-in |

---

## Agent-Agnostic Design

VINCI is not locked to any single AI agent. Every vault contains:

- `CLAUDE.md` — read natively by Claude Code
- `AGENTS.md` — identical mirror read by OpenCode, Codex, and others

The wiki is plain markdown. The graph is a local JSON file. The schema is a text file. Any agent that can read files can maintain VINCI. Switching agents for a session requires only `cd` into the vault and starting the new agent — no rebuilding, no migration.

---

## Core Principles

**No passive storage.** Every input must connect, challenge, or extend something in the wiki.

**Thesis is king.** Every ingest ends with one question: does this shift `thesis.md`?

**Contradictions are signal.** Never smooth over a conflict — file it and let it generate a research question.

**Gaps are where edge is born.** An underdeveloped cluster in the graph is a research opportunity.

**Every insight needs a path to an experiment.** A hypothesis with no proposed test is just a note.

**Output-notes are an audit trail.** Code execution results are never deleted, always processed.

**Final code is evidence.** Cell outputs in notebooks carry the same epistemic weight as empirical results in a paper.

---

## Quick Start

### 1. Install dependencies

```bash
# Wiki skills for Claude Code
git clone https://github.com/NulightJens/ai-second-brain-skills.git ~/ai-second-brain-skills
ln -s ~/ai-second-brain-skills/llm-wiki-setup ~/.claude/skills/llm-wiki-setup
ln -s ~/ai-second-brain-skills/wiki-self-heal ~/.claude/skills/wiki-self-heal

# Graph extraction (handles code, PDFs, images, YouTube)
pip install graphifyy --break-system-packages
graphify install
graphify opencode install

# Session memory
npx claude-mem install
npx claude-mem install --ide opencode

# Optional: blast-radius analysis for codebases
pip install code-review-graph --break-system-packages
code-review-graph install
```

### 2. Create vault structure

```bash
cd ~/VINCI/quant-research

mkdir -p raw/{papers,articles,notion-exports,assets}
mkdir -p codes/{final,iterations}
mkdir -p output-notes/processed
mkdir -p gap-engine
mkdir -p graphify-out
mkdir -p wiki/{papers,strategies,methods,concepts,authors,contradictions,questions,insights,experiments}

echo "codes/iterations/\ngraphify-out/transcripts/\n*.DS_Store" >> .gitignore
```

### 3. Place schema files

Copy `CLAUDE.md` and `AGENTS.md` from this repository into `~/VINCI/quant-research/`.

### 4. Open in Obsidian

Open Obsidian → "Open folder as vault" → select `~/VINCI/quant-research`.

Install community plugins: Obsidian Web Clipper, Dataview, Marp, Graph Analysis.

In Settings → Files and links → set attachment folder to `raw/assets`.

### 5. Bootstrap with Claude Code

```bash
cd ~/VINCI/quant-research
claude
```

```
"Read CLAUDE.md and confirm you understand the VINCI quant vault schema.
Then set up an LLM wiki at this directory using the llm-wiki-setup skill."
```

### 6. First ingest

Drop a paper into `raw/papers/`, then:

```bash
/graphify ./raw --update
```

```
"Ingest the paper I just added to raw/papers/. Use GRAPH_REPORT.md for cross-linking context."
```

---

## Daily Workflow

**Adding a paper:**
```bash
/graphify ./raw --update
# In agent: "Ingest raw/papers/<filename>"
git add . && git commit -m "ingest: <paper title>"
```

**Adding a YouTube video:**
```bash
/graphify add <youtube-url>
```

**After running research code:**
```bash
# Move validated notebook to codes/final/
/graphify ./codes/final --update
# In agent: "Process output-notes and update experiments"
```

**Weekly maintenance (Sunday):**
```bash
# In agent:
"Run wiki-self-heal — dry run first"
"Run gap analysis on this vault"
"Update thesis.md based on experiments completed this week"
git add . && git commit -m "weekly: <date>"
```

---

## YouTube Integration

VINCI uses Graphify's native video pipeline instead of manual note folders. No `youtube-learnings/` directory is needed.

```bash
/graphify add https://youtube.com/watch?v=...
```

Graphify downloads audio-only, transcribes locally with Whisper (nothing leaves your machine), extracts concepts, and integrates the transcript into the knowledge graph. Transcripts are cached so re-runs are instant.

---

## What VINCI Is Not

- Not a SaaS product or hosted service
- Not a replacement for reading — it is an infrastructure for thinking
- Not optimized for teams or production applications
- Not dependent on vector databases, embeddings, or cloud APIs beyond your chosen agent

---

## Inspiration and Credits

- **Pattern**: [Andrej Karpathy's LLM wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- **Wiki skills**: [NulightJens/ai-second-brain-skills](https://github.com/NulightJens/ai-second-brain-skills)
- **Graph extraction**: [safishamsi/graphify](https://github.com/safishamsi/graphify)
- **Session memory**: [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem)
- **Code graph**: [tirth8205/code-review-graph](https://github.com/tirth8205/code-review-graph)

---

## License

MIT — use, fork, and adapt freely.
