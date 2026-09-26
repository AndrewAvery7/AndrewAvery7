<h1 align="center">Andrew Avery</h1>

<p align="center">
  <b>A system's own status report is a claim, not evidence.</b>
</p>

<p align="center">
  Senior product and operations leader — 15+ years of P&amp;L turnarounds, PMO leadership and<br>
  strategic portfolios in retail energy — now building the tooling that checks<br>
  whether AI systems are telling the truth about themselves.
</p>

<p align="center">
  <a href="https://averyresume.com">averyresume.com</a>
  &nbsp;·&nbsp;
  <a href="https://linkedin.com/in/andrewavery">LinkedIn</a>
  &nbsp;·&nbsp;
  <a href="https://cal.com/andrewavery7/30min">Book 30 minutes</a>
  &nbsp;·&nbsp;
  <a href="mailto:andrew@averyemail.com">andrew@averyemail.com</a>
</p>

---

## Three projects. One rule.

Each of these began the same way. A tool reported a result, and the result was not true.

| Project | What the tool reported | What was actually happening |
|---|---|---|
| **[claude-codex-bridge](https://github.com/AndrewAvery7/claude-codex-bridge)** | Transfer failed. | The transfer had **succeeded**. Codex writes ledger paths with the Windows `\\?\` extended-length prefix; the lookup compared them against `realpathSync` output, which does not carry it. Two spellings of the same path, never equal. |
| **[claude-markitdown-hook](https://github.com/AndrewAvery7/claude-markitdown-hook)** | Conversion succeeded. Exit code 0. | **Nothing had been extracted.** An image-only PDF has no text layer, so the converter writes an empty file and exits clean. Hand that to a model and it will tell you, with total confidence, that your document is blank. |
| **[PromptSpend](https://github.com/AndrewAvery7/promptspend)** | 70 prices, all confirmed this morning. | Twelve of them carried a confirmation date **one day after** the verification that supposedly produced it. A price cannot be confirmed tomorrow. The catalogue was describing work that had never happened. |

The first two were other people's software. The third was mine, which is the harder version of the same discipline.

---

### [PromptSpend](https://github.com/AndrewAvery7/promptspend) — LLM pricing that shows its work

Every LLM cost calculator on the web is a snapshot: someone hard-codes a dozen prices and within
months the premise is wrong. PromptSpend is built the other way round — **the pipeline is the product.**
Every morning a GitHub Action re-checks 80 models across 12 providers, merges sources under an explicit
trust order, and a run that loses a source or would shrink the catalogue publishes nothing and fails loudly.

The differentiator is provenance, not breadth. Competitors advertise more models. Here every price carries
the vendor page it was read from and the date it was read, and prices two sources disagree about are
**marked rather than quietly resolved**. 58 of the 80 have been read against a vendor's own page; the other
22 stay labelled as feed-sourced, because using an aggregator to close that gap would launder a third
party's number into a first-party claim.

Answers in five places — [the site](https://promptspend.com), including a Receipt you paste into an existing AI
conversation for a one-response cost audit; free native apps for
[iPhone](https://apps.apple.com/app/id6800386428) and [Android](https://play.google.com/store/apps/details?id=com.promptspend.app)
that price a pasted conversation on the device; a keyless CORS-open API with an OpenAPI 3.1 description; an MCP
server on npm so a coding agent gets the same figures with the same paperwork; and a VS Code extension that
annotates a model id inline with its rate and the date it was last confirmed. Price changes arrive by Atom feed,
browser push or double-opt-in email, and the catalogue's own change history is what the
[August 2026 Price Movement Report](https://promptspend.com/writing/2026-08-price-movement-report/) is written from.
1,232 automated tests across seven suites, 164 of them in a real browser across four viewports, axe auditing
at WCAG 2.1 A/AA. No accounts, no analytics, no cookies.

https://github.com/user-attachments/assets/8ddf3e53-2a97-4d86-ac93-d09507c387de

<sub><i>2 minutes 8 — press play, and hit 🔊 to unmute (GitHub starts videos silent).</i></sub>

### [claude-markitdown-hook](https://github.com/AndrewAvery7/claude-markitdown-hook) — cheap, honest document ingestion

Converts the PDFs and Office files you mention to markdown and hands Claude Code a **pointer** rather than
the contents, so referencing a large document costs almost nothing until its contents actually matter.

Because the underlying converter exits 0 on an empty extraction, every conversion is **graded on the text it
actually recovered** — PDFs by characters per page against a threshold chosen from measured documents.
Image-only PDFs measure 0–40 characters per page; real text PDFs measure 650–950; the default threshold of
100 sits in the gap between them. A failed extraction writes no file and tells Claude to read the original
with vision instead. 41 tests, twelve formats, CI across Windows, macOS and Linux on Python 3.10 and 3.12.
No OCR, no server, no telemetry.

### [claude-codex-bridge](https://github.com/AndrewAvery7/claude-codex-bridge) — hand a live session to another model

One command moves a running Claude Code session into OpenAI Codex with the conversation, skills, operating
instructions and memory layer intact — and opens the Codex desktop app directly on the transferred thread.
A desktop launcher does the same without spending a Claude token, which matters when you are rate-limited.

The Windows false-failure diagnosis above was submitted upstream as
[codex-plugin-cc#551](https://github.com/openai/codex-plugin-cc/pull/551): a 19-line fix, unit-tested, verified
against a real Windows 11 ledger. It was closed without review after the repository went quiet;
the bug is still there, now tracked upstream as [issue #618](https://github.com/openai/codex-plugin-cc/issues/618).
The fix ships here instead — this kit detects the imported thread directly in Codex's state database, because
it trusts the evidence rather than the success message.

---

## Before the code

Fifteen years of running operations where being wrong is expensive, which is where the habit comes from.

- Returned a **$25M annual-loss business unit to profitability in 12 months** at NRG Energy.
- Took **$91.6M out of the cost base in three years** against a four-year plan at Direct Energy — beating the target by $12.8M, 14% over.
- Stood up a **PMO from scratch** across multi-segment GTM partnerships; managed five team leads across ~30 staff.
- Served on the executive leadership team accountable for NRG's **M&A divestiture**, which unified the operating model and consolidated cross-functional teams.
- Redesigned customer engagement at Direct Energy: **retention +11%**, revenue **+$100K in the first month**.

Currently Senior Manager, Business Performance &amp; Strategic Initiatives at NRG Energy (Fortune 150), running
the strategic-initiative portfolio for a multi-segment retail energy and home-protection P&amp;L, working with the
C-suite on prioritization, capital allocation and performance reporting — and expanding that remit into
evaluating generative-AI use cases against ROI, accuracy and risk criteria.

## Now

Post-graduate **AI &amp; Machine Learning: Business Applications** at UT Austin (McCombs), in progress — four graded
builds spanning multi-agent automation, RAG document analysis, predictive-maintenance networks and clinical
decision support. The first build, a wind-turbine drivetrain-fault classifier, is complete, and a program hackathon
on restaurant revenue, built with Claude Cowork, placed 7th of 53; both are written up in full at
[averyresume.com/mccombs.html](https://averyresume.com/mccombs.html). Executive education in AI strategy at **UC Berkeley (Haas)**. 19 AI certifications alongside
CSM, CAL-E and CPP.

Ships code daily with Claude Code and Cursor, with evidence-based judgment about where LLM-assisted
development helps and where it does not — evidenced by the three repositories above rather than asserted.

---

<p align="center">
  <b>Open to senior product, operations and AI leadership roles and contract engagements.</b><br>
  Industry-open.
</p>

<p align="center">
  <a href="https://cal.com/andrewavery7/30min">Book 30 minutes</a>
  &nbsp;·&nbsp;
  <a href="mailto:andrew@averyemail.com">andrew@averyemail.com</a>
  &nbsp;·&nbsp;
  <a href="https://averyresume.com/resume-request.html">Résumé</a>
  &nbsp;·&nbsp;
  <a href="https://linkedin.com/in/andrewavery">LinkedIn</a>
</p>
