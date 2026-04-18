# VINCI — Quant Research Vault

## Purpose
A self-improving research engine for quantitative finance.
Goal: generate and validate trading edge through structured knowledge,
gap detection, and iterative hypothesis testing.

Core loop:
Raw data → Wiki → Graph → Gap detection → Questions → Insights → Experiments → Thesis update → Repeat

---

## Agent-agnostic design
Claude Code reads this file as CLAUDE.md.
OpenCode and Codex read the mirror at AGENTS.md.
Both files are always identical. When you update one, update the other immediately.

---

## Directory layout

```
quant-research/
├── raw/
│   ├── papers/            ← PDFs, arxiv downloads (primary academic sources)
│   ├── articles/          ← web clips, blog posts, practitioner writing
│   ├── notion-exports/    ← Notion page exports in markdown format
│   └── assets/            ← downloaded images and figures
├── codes/
│   ├── final/             ← validated notebooks and scripts WITH outputs (Graphify indexes these)
│   └── iterations/        ← drafts, errors, abandoned logic (gitignored, never indexed)
├── output-notes/          ← results from code execution, staging area before wiki/experiments
├── gap-engine/
│   ├── gaps.md            ← current detected gaps (updated weekly)
│   ├── cluster-analysis.md ← community structure from Graphify GRAPH_REPORT
│   └── prompts.md         ← reusable gap, insight, and falsification prompts
├── graphify-out/
│   ├── graph.json         ← persistent knowledge graph (auto-generated)
│   └── GRAPH_REPORT.md    ← god nodes, clusters, bridges, isolates, suggested questions
├── wiki/
│   ├── papers/            ← one summary page per source
│   ├── strategies/        ← one page per strategy or strategy family
│   ├── methods/           ← statistical and ML methods
│   ├── concepts/          ← market microstructure, risk, factor theory
│   ├── authors/           ← key researchers and body of work
│   ├── contradictions/    ← conflicting claims across sources
│   ├── questions/         ← gap-driven research questions
│   ├── insights/          ← generated hypotheses (alpha candidates)
│   ├── experiments/       ← backtest records and validation results
│   ├── index.md           ← master catalog of every wiki page
│   ├── log.md             ← append-only activity log
│   └── thesis.md          ← evolving beliefs, supported by evidence, falsifiable
├── CLAUDE.md              ← this file (Claude Code)
└── AGENTS.md              ← mirror of this file (OpenCode, Codex, others)
```

---

## Frontmatter (required on every wiki page)

```yaml
---
title:
type: paper | strategy | method | concept | author | contradiction | question | insight | experiment
tags: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: N
---
```

---

## Source hierarchy (epistemic weight, highest to lowest)

1. `raw/papers/` — peer-reviewed or pre-print academic work
2. `codes/final/` — your own empirical results with outputs
3. `output-notes/` — your observations from code execution (staging)
4. `raw/articles/` — practitioner writing, blog posts
5. `raw/notion-exports/` — your own previous notes and exports
6. YouTube — processed via Graphify directly (no folder, see YouTube protocol below)

When claims conflict, weight follows this order. Flag explicitly when a lower-weight source contradicts a higher-weight one.

---

## YouTube protocol (no folder needed)

Do NOT create files manually for YouTube content.
Graphify handles transcription and graph integration natively.

To add a YouTube video to the knowledge graph:
```
/graphify add <youtube-url>
```

Graphify downloads audio-only, transcribes locally with Whisper, extracts concepts,
and integrates the transcript into graph.json automatically.
The transcript is cached in graphify-out/transcripts/ — re-runs skip already-processed URLs.

Only run this for videos with substantive technical content (lectures, conference talks,
strategy walkthroughs). Do not add general commentary or news.

After adding videos, run:
```
/graphify ./raw --update
```
to merge the video concepts with your paper and article concepts.

---

## Graphify commands (run these in order)

```bash
# After adding papers or articles
/graphify ./raw --update

# After moving notebooks or scripts to codes/final/
/graphify ./codes/final --update

# Full combined run (weekly or after major ingestion)
/graphify ./raw --update && /graphify ./codes/final --update

# Add a YouTube video
/graphify add <youtube-url>

# Start MCP server for agent queries
python -m graphify.serve graphify-out/graph.json
```

Graphify handles: .pdf, .md, .txt, .ipynb, .py, .png, .jpg — all in one pass.
Cell outputs in notebooks are treated as evidence, not just code.

---

## Paper ingest protocol

Follow this exactly. Do not skip steps.

1. Run `/graphify ./raw --update` and read `graphify-out/GRAPH_REPORT.md`
2. Discuss key takeaways with me BEFORE writing anything
3. Create `wiki/papers/<author>-<year>-<keyword>.md`:
   - **Core Claim** — 1-2 sentences, no hedging
   - **Method** — what they actually did, precise
   - **Key Results** — numbers, not vague language
   - **Assumptions & Limitations** — be harsh here
   - **Graph connections** — concepts already in graph that link to this paper
   - **Contradicts** — `[[links]]` to wiki pages this challenges
   - **Supports** — `[[links]]` to wiki pages this strengthens
   - **My Take** — opinionated, written after our discussion
4. Create or update `wiki/methods/` pages the paper touches
5. Create or update `wiki/strategies/` pages the paper touches
6. Create or update `wiki/authors/<name>.md`
7. If the paper contradicts existing wiki → create or update `wiki/contradictions/<topic>.md`
8. Update `wiki/index.md` with any new or changed pages
9. Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] ingest | <paper title>
   ```
10. Ask me: "Does this shift thesis.md?"
11. Ask me: "Does this close any open question in wiki/questions/?"

---

## Code ingest protocol (codes/final/)

For notebooks (.ipynb) and scripts (.py) moved to codes/final/:

1. Run `/graphify ./codes/final --update`
2. Discuss key findings with me — focus on what the outputs show, not just the code
3. Check output-notes/ for any related observations already written
4. Create `wiki/experiments/<slug>.md` using this structure:
   - **Hypothesis tested**
   - **Method** — brief description of approach
   - **Data used**
   - **Result** — numbers from cell outputs
   - **Conclusion**
   - **Notebook** — `codes/final/<filename>`
   - **Shifts thesis?** — yes / no / partially, with explanation
5. If the code validates an existing insight → update `wiki/insights/<slug>.md` confidence level
6. If the code generates a new hypothesis → create `wiki/insights/<slug>.md`
7. Update `wiki/index.md` and append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] experiment | <slug>
   ```

---

## Output-notes protocol

output-notes/ is a staging area — results land here after code execution,
before they are synthesized into wiki/experiments/.

When I say "process output-notes":
1. Read all files in output-notes/ that haven't been processed yet
2. For each file, identify which codes/final/ notebook it corresponds to
3. Merge observations with the relevant wiki/experiments/ page, or create one if missing
4. Once processed, move the file to output-notes/processed/ (create this subfolder if needed)
5. Never delete output-notes — they are an audit trail

---

## Gap engine protocol

Trigger: "Run gap analysis" or as part of weekly wiki-self-heal

1. Read `graphify-out/GRAPH_REPORT.md` — focus on isolates and weak clusters
2. Read `gap-engine/cluster-analysis.md`
3. Read `wiki/thesis.md`
4. Identify all four gap types:

   **DISCONNECTED** — cluster pairs with no bridge nodes between them
   Example: OI analysis cluster ↔ volatility models cluster, no connecting concepts

   **WEAK** — topics with fewer than 3 source papers, or concepts with no linked experiments

   **CONTRADICTION** — conflicts in wiki/contradictions/ that remain unresolved

   **THESIS** — beliefs stated in thesis.md with no supporting wiki/experiments/ entry

5. Update `gap-engine/gaps.md` with all findings, dated
6. Update `gap-engine/cluster-analysis.md` with current god nodes, bridges, and isolates
7. For each significant gap, create `wiki/questions/<slug>.md`:
   ```
   ---
   title:
   type: question
   tags: []
   created: YYYY-MM-DD
   gap_source:
   status: open
   ---

   ## Gap identified

   ## Clusters involved

   ## Why it matters for the thesis

   ## Research question

   ## Related concepts

   ## Leads
   ```
8. Output a summary: "X gaps found, Y new questions created"

---

## Question → insight protocol

Trigger: "Generate insights from open questions"

For each `wiki/questions/` page with `status: open`:
1. Read the gap description and related concepts
2. Read `GRAPH_REPORT.md` for structural connections between the clusters
3. Generate 1-2 hypotheses that could bridge the gap
4. Create `wiki/insights/<slug>.md`:
   ```
   ---
   title:
   type: insight
   tags: []
   created: YYYY-MM-DD
   confidence: low
   status: hypothesis
   ---

   ## Hypothesis

   ## Proposed mechanism

   ## Supporting evidence

   ## What would falsify this

   ## Experiment designed
   ```
5. Set confidence: low (unvalidated)
6. Update the source question page: status: in-progress, link to insight

---

## Insight → experiment protocol

Trigger: "Design experiment for <insight>"

1. Read `wiki/insights/<slug>.md`
2. Design the minimal viable test:
   - What data is needed?
   - What does confirmation look like vs refutation?
   - What code structure would test this?
3. Create `wiki/experiments/<slug>.md` with `status: designed`
4. Link back from the insight page to the experiment
5. Ask me: "Do you want to start the notebook for this now?"

---

## Query protocol

When answering any question against the wiki:
1. Read `wiki/index.md` — find the relevant pages
2. Read `wiki/thesis.md` — understand current beliefs
3. Read `gap-engine/gaps.md` — note known blind spots relevant to the question
4. Read the relevant wiki pages, cite with `[[wikilinks]]`
5. Flag explicitly if the answer contradicts thesis.md
6. Ask: "Should I file this answer as a wiki page?"

---

## Lint protocol (weekly, run every Sunday)

```
"Run wiki-self-heal on this vault — dry run first, show me the audit report"
```

After wiki-self-heal, also run gap analysis manually.

Check for:
- Claims in wiki/ superseded by newer sources
- Insights stuck at `status: hypothesis` for more than 4 weeks — escalate or close
- Experiments with `status: designed` but no linked notebook — follow up
- Experiments missing a Conclusion section
- thesis.md beliefs with zero supporting experiments
- Authors cited 3+ times without an `authors/` page
- Concepts mentioned in multiple pages but lacking their own page
- Output files in output-notes/ not yet processed

Output: audit report + 3-5 new papers or data sources to find, based on open gaps

---

## Commit convention

After each significant session:
```bash
git add .
git commit -m "ingest: <title>" | "experiment: <slug>" | "gap-analysis: <date>" | "thesis: <what changed>"
```

Keep iterations/ gitignored — only final/ and wiki/ are tracked.

---

## Core principles

**No passive storage.** Every input must connect, challenge, or extend something already in the wiki.

**Thesis is king.** Every ingest ends with: does this shift thesis.md?

**Contradictions are signal, not noise.** Never smooth over a conflict — file it in wiki/contradictions/ and let it generate a question.

**Gaps are where edge is born.** An underdeveloped cluster is a research opportunity.

**Every insight needs a path to an experiment.** A hypothesis with no proposed test is just a note.

**Output-notes are an audit trail.** Never delete them, always process them.

**Final code is evidence.** Cell outputs are data. Treat them with the same weight as empirical results from a paper.