# SignalPilot Documentation Restructuring Plan

**Status:** Draft for Review
**Created:** 2026-01-07
**Goal:** Transform docs from "Jupyter plugin" positioning → "Context Orchestration Engine" with proper CLI bootstrap framing

---

## 🎯 Executive Summary

### The Core Problem

Current docs position SignalPilot as "AI-powered Jupyter extension" when the actual innovation is:
- **Context Orchestration Engine** that aggregates organizational knowledge (dbt, Slack, Jira, query history)
- **Production-ready Agent Loop** with MCP sidecar, multi-session memory, and hooks
- **Delivered via Jupyter/VSCode** (the extension is the delivery method, not the product)

### Critical Misalignments

1. **CLI docs** ([cli-docs.md](new-doc-spec/cli-docs.md)) position CLI as primary product, when CLI is actually a **bootstrap installer** for the Jupyter extension
2. **Old docs** say "AI-powered extension" — **Aurora One Pager** says "Context Orchestration for AI-native Data Teams"
3. **Agent loop innovations** (MCP sidecar, memory, hooks) are invisible in current docs
4. **No comparison** showing why SignalPilot vs ChatGPT + Jupyter
5. **No "How It Works"** architecture page showing the orchestration loop

---

## 📊 Gap Analysis from Best-in-Class Research

Based on analysis of: uv, Cursor, Cline, Continue.dev, Vercel AI SDK, LangChain, Stripe

### 🔴 CRITICAL GAPS (Blocking Adoption)

| Gap | Current State | Required State | Pattern Source |
|-----|--------------|----------------|----------------|
| **Value Prop** | "AI-powered Jupyter extension" | "Context Orchestration Engine that connects to dbt/Slack/Jira/query history that ChatGPT can't access" | Aurora One Pager + Cursor |
| **CLI Positioning** | Primary product | Bootstrap installer for Jupyter extension | uv (CLI as installer tool) |
| **Architecture Visibility** | Hidden | "How SignalPilot Works" page showing MCP sidecar + agent loop + memory | Vercel AI SDK (Foundations) |
| **Comparison** | None | "Why SignalPilot vs ChatGPT/Copilot" comparison table | Cursor, uv |
| **Control Mechanisms** | Vague | Document approval workflows, hooks, scope control BEFORE autonomous features | Cline |

### 🟡 HIGH IMPACT (Improves UX)

| Gap | Fix | Pattern Source |
|-----|-----|----------------|
| **Feature vs Task Org** | Reorganize: "Investigating Revenue Drops" not "Planning Mode" | Cursor, Stripe |
| **No Executable Examples** | Show command + expected output at every step | uv |
| **Security Buried** | Elevate to Introduction section with MCP architecture | Continue.dev |
| **No Quickstart Outcome** | "Analyze Stripe revenue in 5 min" with time commitment | Stripe |

---

## 🏗️ Proposed Information Architecture

### New Structure

```
📚 SignalPilot Docs

📖 Introduction
  ├─ What is SignalPilot? ⭐ NEW
  │   └─ Context Orchestration Engine positioning (Aurora One Pager)
  │
  ├─ Why SignalPilot vs ChatGPT + Jupyter ⭐ NEW
  │   └─ Comparison table: what context can SignalPilot access that others can't
  │
  ├─ How SignalPilot Works ⭐ NEW
  │   ├─ MCP Sidecar Architecture (internal + external servers)
  │   ├─ Agent Orchestration Loop (resolve → build → call → execute → stream)
  │   ├─ Multi-Session Memory (institutional knowledge)
  │   └─ Modular Hooks System (custom constraints)
  │
  └─ Security & Privacy ⭐ EXPANDED
      ├─ MCP Read-Only Access Model
      ├─ Scope Control (choose which schemas/projects)
      ├─ Zero Data Retention
      ├─ SOC 2 Status
      └─ Audit Trail

🚀 Getting Started
  ├─ Installation ⭐ RESTRUCTURED (from cli-docs.md)
  │   ├─ What You're Installing (Jupyter extension, CLI is bootstrap)
  │   ├─ Quick Start (uvx signalpilot)
  │   ├─ Advanced: Working in Different Directories (--here, --project)
  │   ├─ CLI Reference (init, lab, doctor, upgrade)
  │   ├─ Package Management (uv)
  │   └─ Troubleshooting
  │
  ├─ Quickstart: First Analysis in 5 Minutes ⭐ NEW
  │   ├─ Time commitment stated
  │   ├─ Working example with real outcome
  │   ├─ Expected output shown
  │   └─ Success criteria defined
  │
  └─ Key Concepts ⭐ ENHANCED
      ├─ Context Aggregation (what is context, where from, how used)
      ├─ Agents & Modes (Agent, Hands-On, Ask)
      ├─ Planning & Iteration (multi-step workflows)
      ├─ @ Mentions (context scoping)
      └─ Hooks (custom rules)

📝 Guides (Task-Oriented) ⭐ NEW ORGANIZATION
  ├─ Investigating Revenue Drops
  │   └─ Shows: Planning + dbt lineage + Slack context + iteration
  │
  ├─ Debugging Data Quality Issues
  │   └─ Shows: Schema introspection + query history + hypothesis testing
  │
  ├─ Analyzing Time-Series Trends
  │   └─ Shows: Visualization + cell editing + iteration loop
  │
  ├─ Working with dbt Projects
  │   └─ Shows: Lineage graph + metadata + upstream dependencies
  │
  └─ Customizing with Hooks
      └─ Shows: Pre-execution validation + data quality checks + audit logging

🔌 Integrations ⭐ REORGANIZED
  ├─ MCP Overview (what is MCP, why MCP vs direct connections)
  │
  ├─ Database Connections
  │   ├─ Popular: PostgreSQL, Snowflake, Databricks
  │   └─ More: MySQL, BigQuery, Redshift (alphabetical)
  │
  ├─ dbt Integration (Cloud + Core)
  │
  └─ Collaboration Tools (MCP Subagents)
      ├─ Slack (threads, discussions)
      ├─ Jira (tickets, issues)
      └─ GDocs/Notion (design docs)

🔧 Reference
  ├─ Agent Modes Deep Dive
  │   ├─ Agent Mode (automation + control mechanisms)
  │   ├─ Hands-On Mode (manual context control)
  │   └─ Ask Mode (read-only)
  │
  ├─ Cell-Level Editing
  │   ├─ Inline Edit (single cell modifications)
  │   └─ Tab Autocomplete (context-aware suggestions)
  │
  ├─ CLI Commands
  │   ├─ uvx signalpilot / sp init
  │   ├─ sp lab [--here|--project]
  │   ├─ sp doctor
  │   └─ sp upgrade
  │
  ├─ Configuration Reference
  │   ├─ Hooks Configuration
  │   ├─ MCP Server Settings
  │   └─ Agent Behavior
  │
  └─ Troubleshooting Guide

🎓 Deep Dives (Advanced)
  ├─ Understanding Context Aggregation
  │   └─ MCP sidecar architecture internals
  │
  ├─ Agent Orchestration Loop
  │   └─ Production-ready loop mechanics
  │
  ├─ Multi-Session Memory
  │   └─ What it stores, how it works, persistence
  │
  ├─ Hooks System
  │   └─ Custom constraints, validations, audit
  │
  └─ Extended Thinking (Claude Sonnet 4.5)
      └─ How reasoning phase works
```

---

## 🔄 Content Migration Map

### Files to Create (NEW)

| File | Source | Purpose |
|------|--------|---------|
| `introduction/what-is-signalpilot.md` | Aurora One Pager | Context orchestration positioning |
| `introduction/why-signalpilot.md` | Analysis above | Comparison vs ChatGPT/Copilot |
| `introduction/how-it-works.md` | Architecture diagram | MCP + Agent Loop + Memory |
| `getting-started/installation.md` | **cli-docs.md** (restructured) | Bootstrap installer framing |
| `getting-started/quickstart.md` | New content | 5-min outcome-focused tutorial |
| `guides/investigating-revenue.md` | New content | Task-based example |
| `guides/debugging-data-quality.md` | New content | Task-based example |
| `guides/analyzing-timeseries.md` | New content | Task-based example |
| `guides/working-with-dbt.md` | New content | Task-based example |
| `guides/customizing-hooks.md` | New content | Extensibility guide |

### Files to Restructure (MAJOR CHANGES)

| Current File | New Location | Changes |
|--------------|-------------|---------|
| `new-doc-spec/cli-docs.md` | `getting-started/installation.md` | **CRITICAL:** Reframe as installation guide, not product overview. CLI is bootstrap tool for Jupyter extension. |
| `old-docs/overview/overview.md` | `introduction/what-is-signalpilot.md` | Replace "AI-powered extension" with "Context Orchestration Engine" |
| `old-docs/overview/concepts.md` | `getting-started/key-concepts.md` | Add MCP, memory, hooks. Expand mental models. |
| `old-docs/overview/security-and-privacy.md` | `introduction/security-and-privacy.md` | Add MCP architecture, scope control, SOC 2, audit trail |

### Files to Reorganize (TASK-BASED)

| Current (Feature-Based) | New (Task-Based) | Why |
|------------------------|------------------|-----|
| `old-docs/core/agents/` (Overview, Chat, Planning, Modes) | Split into Guides (task-oriented) + Reference (deep dive) | Users think in tasks, not features |
| `old-docs/core/connecting-databases/` (PostgreSQL, MySQL, etc.) | Move to `integrations/databases/` with Popular vs More tiers | Reduce cognitive load |
| `old-docs/core/cell-level-edit/` | Move to `reference/cell-editing/` | These are reference materials, not guides |

### Files to Keep (MINOR UPDATES)

| File | Updates Needed |
|------|---------------|
| `old-docs/tutorials/ai-agents-jupyter-2025.md` | Add context about MCP, memory. Show it's not just code generation. |
| `old-docs/tutorials/connect-database.md` | Add MCP framing. Show what context this provides. |
| `old-docs/core/connecting-databases/*.md` | Add "What context this provides" section showing how it improves analysis |

---

## 🎨 Key Content Rewrites

### 1. Installation Page (from cli-docs.md)

**BEFORE (current cli-docs.md):**
```markdown
# SignalPilot CLI
Your Trusted CoPilot for Data Analysis - A simple CLI tool...

## Features
- 🚀 One-command setup
```

**AFTER (new installation.md):**
```markdown
# Installation

Get SignalPilot up and running in under 3 minutes.

## What You're Installing

SignalPilot is a **Jupyter Lab extension** (soon VSCode) with:
- AI agent with full organizational context (dbt, databases, Slack, etc.)
- MCP-powered context aggregation
- Multi-step planning and execution
- Cell-level editing and autocomplete

The SignalPilot CLI is a **bootstrap tool** that:
1. Creates your workspace (~/SignalPilotHome)
2. Installs Jupyter Lab + SignalPilot extension
3. Manages Python environments and packages
4. Launches Jupyter with SignalPilot pre-configured

---

## Quick Start

```bash
# No installation needed - runs via uvx
uvx signalpilot
```

**What happens:**
✓ Creates `~/SignalPilotHome` workspace
✓ Installs Python 3.12 + Jupyter Lab + SignalPilot extension
✓ Sets up data science packages (pandas, numpy, matplotlib, plotly)
✓ Launches Jupyter Lab in your browser

**Time:** ~2-3 minutes

[Continue with CLI Reference, Package Management, Troubleshooting...]
```

**Key Changes:**
- Clarify Jupyter extension is the product
- CLI is installer/bootstrap tool
- Add expected output at every step
- Frame around "what you're getting" not "what the CLI does"

---

### 2. "What is SignalPilot?" Landing Page

**BEFORE (current overview.md):**
```markdown
SignalPilot is an AI-powered extension for Jupyter Notebooks. It can:
- write, debug and run jupyter code cells
- create and interpret plots
- read, understand, and analyze tabular data
```

**AFTER (new what-is-signalpilot.md):**
```markdown
# What is SignalPilot?

## Context Orchestration for AI-native Data Teams

When leadership asks "why did remote assist interventions spike last week?" —
the answer lives across your dbt models, S3 transformation logic, design docs,
Jira tickets about recent changes, and Slack threads where your team already
debugged a related issue.

**The Problem:**
Analysts spend 80% of investigation time re-collecting context that already
exists somewhere. Claude, Cursor, and Copilot accelerate the last mile of
writing code — but can't help with the first mile of knowing *what* to look
for and *where* the truth lives.

**The Solution:**
SignalPilot is a Jupyter-native AI agent with a **context orchestration layer**
purpose-built for data investigation. It can reason about your data because it
has access to your full organizational context.

### We Connect (Read-Only) To:

- **Warehouses** (Snowflake, Databricks, Postgres): schemas, query history, data profiles
- **dbt projects:** model definitions, lineage, transformation logic
- **Collaboration tools** (Slack, GDocs, Notion, Jira) via MCP Subagents: past decisions, threads
- **Notebooks & analysis history:** prior conclusions, validated assumptions

### How It Works at [Your Company]:

1. Analyst receives question: *"Why did on-road event detection rates change after last week's deploy?"*

2. SignalPilot agent (running in Jupyter):
   - Identifies relevant dbt models and upstream S3 sources
   - Pulls the Jira ticket for the recent deploy and linked design doc
   - Finds a Slack thread where a teammate flagged a related anomaly
   - Checks transformation lineage for schema drift

3. Agent **plans, iterates,** and **executes** targeted queries to validate hypotheses
   — grounded in actual context, not hallucinated table names

4. Delivers an investigation report your C-suite can act on
   — with provenance back to source systems

### Why This Isn't Another Tool to Manage

Claude and Cursor are general-purpose coding assistants, while SignalPilot is
purpose-built for data investigation — it runs where your analysis already lives
(Jupyter, soon VS Code) and connects to context those tools can't access.

**Think of it as:** The difference between giving an intern a database connection
vs. giving them 6 months of institutional knowledge about how your data actually works.

[See comparison table →](why-signalpilot.md)
[Understand the architecture →](how-it-works.md)
```

**Key Changes:**
- Lead with Aurora One Pager positioning
- Use actual user pain point (investigation time)
- Show what context SignalPilot accesses that others can't
- Include real-world workflow example
- Clear differentiation from ChatGPT/Cursor/Copilot

---

### 3. "How SignalPilot Works" Architecture Page

**NEW PAGE** (based on orchestration diagram):

```markdown
# How SignalPilot Works

SignalPilot is a **context orchestration engine** that gives AI agents
access to your full organizational knowledge.

## The Problem with Traditional AI Coding Assistants

When you ask ChatGPT or Copilot:
> "Why did remote assist interventions spike last week?"

They can't answer because:
- ❌ No access to your dbt model lineage
- ❌ No access to recent Jira tickets about changes
- ❌ No access to Slack threads where issues were discussed
- ❌ No access to query history showing anomalies
- ❌ No memory of past investigations

They can only see the code you copy-paste.

## SignalPilot's Solution: Three Innovations

### 1. Multi-Source Context Aggregation (MCP Sidecar)

SignalPilot connects to your data stack via **MCP (Model Context Protocol):**

```
┌─────────────────────────────────────────────┐
│ SignalPilot Internal MCP Sidecar           │
├─────────────────────────────────────────────┤
│ • Kernel Ops (execute code, introspect)    │
│ • DB Queries (schemas, query history)      │
│ • Schema Introspection (metadata, lineage) │
│ • Kernel Variables (dataframes, state)     │
│ • Local Files (notebooks, CSVs, config)    │
└─────────────────────────────────────────────┘
                     +
┌─────────────────────────────────────────────┐
│ External MCP Servers (various languages)   │
├─────────────────────────────────────────────┤
│ • dbt Cloud/Core (lineage, documentation)  │
│ • Slack (threads, decisions, discussions)  │
│ • Jira (tickets, issues, changes)          │
│ • GDocs/Notion (design docs, wikis)        │
│ • Snowflake/Databricks (query logs, stats) │
└─────────────────────────────────────────────┘
```

**Result:** SignalPilot can reason across:
- Database schemas + query performance
- dbt model lineage + transformations
- Past Slack discussions about data issues
- Jira tickets about recent deploys
- Historical notebook investigations

### 2. Production-Ready Agent Orchestration Loop

Unlike single-shot completions, SignalPilot runs a **continuous orchestration loop:**

```
┌──────────────────────────────────────────────────┐
│ 1. Resolve Contexts (PARALLEL)                  │
│    - Fetch relevant schemas                     │
│    - Load dbt lineage                           │
│    - Find related Slack threads                 │
│    - Retrieve past investigation notebooks      │
└──────────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────────┐
│ 2. Build System Prompt (with aggregated context)│
└──────────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────────┐
│ 3. Call LLM (Stream Response)                   │
│    - Extended thinking (Claude Sonnet 4.5)      │
│    - Tool use (execute code, query DB)          │
└──────────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────────┐
│ 4. Execute Tools (PARALLEL)                     │
│    - Kernel ops, DB queries, schema checks      │
└──────────────────────────────────────────────────┘
                     ↓
┌──────────────────────────────────────────────────┐
│ 5. Stream Results + Continuous Completion Check │
│    - Loop until done or user stops              │
└──────────────────────────────────────────────────┘
```

**Key innovations:**
- Parallel context resolution (fast, doesn't block LLM)
- Continuous completion checking (knows when to stop)
- Tool execution in parallel (efficient)
- Multi-step iteration (not single-shot)

### 3. Multi-Session Memory & Hooks

**Memory:**
- Analysis history (what hypotheses were tested? ruled out?)
- Validated assumptions ("Revenue calculation uses net, not gross")
- Known data quirks ("Orders table has duplicates before 2024")
- Past solutions ("Last time this spiked, it was timezone issues")

**Hooks:**
- Pre-execution validation ("Only query prod DB during office hours")
- Data quality checks ("Warn if row count changed >20%")
- Custom rules ("Always use vectorized pandas, never loops")
- Audit logging (track what data was accessed and when)

## Comparison: SignalPilot vs Alternatives

| Capability | ChatGPT + Jupyter | GitHub Copilot | SignalPilot |
|------------|-------------------|----------------|-------------|
| Code completion | ❌ Manual | ✅ Inline | ✅ Tab autocomplete |
| Database schema awareness | ❌ Copy-paste | ❌ | ✅ Auto via MCP |
| dbt lineage | ❌ | ❌ | ✅ Full graph |
| Slack/Jira context | ❌ | ❌ | ✅ MCP subagents |
| Multi-step planning | ❌ Single-shot | ❌ | ✅ Orchestrated loop |
| Multi-session memory | ❌ | ❌ | ✅ Persistent |
| Query history analysis | ❌ | ❌ | ✅ Via MCP |
| Institutional knowledge | ❌ | ❌ | ✅ Via memory + MCP |

**Bottom line:** SignalPilot is the only tool that can answer questions
like "Why did X spike?" by aggregating context across your entire data
stack + organizational knowledge.

## Security & Control

Despite broad access, you maintain full control:
- **Read-only MCP connections** (no writes to prod systems)
- **Scope control** (choose which schemas/projects to connect)
- **Approval workflows** (Planning Mode requires confirmation)
- **Hooks constraints** (enforce custom rules)
- **Local-first execution** (code runs in your environment)
- **Zero data retention** (no data stored on SignalPilot servers)
- **Audit trail** (see what context was accessed)

[Learn more about security →](security-and-privacy.md)
```

---

## 📋 Implementation Phases

### Phase 1: Critical Positioning (Week 1) 🔴

**Goal:** Fix positioning and CLI confusion

**Deliverables:**
1. ✅ **Restructure cli-docs.md → installation.md**
   - Reframe as installation guide
   - Clarify Jupyter extension is product, CLI is installer
   - Add executable examples with expected output
   - Files: `getting-started/installation.md`

2. ✅ **Create "What is SignalPilot?" landing page**
   - Aurora One Pager positioning
   - Context orchestration framing
   - Real-world workflow example
   - Files: `introduction/what-is-signalpilot.md`

3. ✅ **Create "How SignalPilot Works" architecture page**
   - MCP sidecar diagram
   - Agent orchestration loop
   - Memory + hooks
   - Files: `introduction/how-it-works.md`

4. ✅ **Create comparison page**
   - Why SignalPilot vs ChatGPT/Copilot
   - Context access comparison table
   - Files: `introduction/why-signalpilot.md`

5. ✅ **Expand Security & Privacy page**
   - MCP read-only architecture
   - Scope control
   - SOC 2 status
   - Audit trail
   - Files: `introduction/security-and-privacy.md`

**Success Criteria:**
- [ ] New visitor can understand "Context Orchestration Engine" positioning in <30 seconds
- [ ] Clear differentiation from ChatGPT/Copilot
- [ ] No confusion about CLI vs extension
- [ ] Architecture diagram visible and understandable

---

### Phase 2: Task-Based Guides (Week 2) 🟡

**Goal:** Reorganize from feature-based → task-based

**Deliverables:**
1. ✅ **Create task-oriented guides**
   - `guides/investigating-revenue-drops.md` (shows full orchestration)
   - `guides/debugging-data-quality.md` (schema + query history)
   - `guides/analyzing-timeseries.md` (visualization + iteration)
   - `guides/working-with-dbt.md` (lineage + metadata)
   - `guides/customizing-hooks.md` (extensibility)

2. ✅ **Reorganize existing content**
   - Move agents/ content into guides + reference split
   - Move connecting-databases/ to integrations/ with Popular/More tiers
   - Move cell-level-edit/ to reference/

3. ✅ **Add "What context this provides" sections**
   - All database connection docs
   - All integration docs
   - Show how context improves analysis

**Success Criteria:**
- [ ] User searching for "how to investigate revenue drops" finds task guide, not feature list
- [ ] Every guide shows working example with expected output
- [ ] Database docs explain what context is provided (not just how to connect)

---

### Phase 3: Reference & Polish (Week 3) 🟢

**Goal:** Complete reference docs and add polish

**Deliverables:**
1. ✅ **CLI Reference documentation**
   - Complete command reference with examples
   - Expected output shown for each command
   - Troubleshooting guide
   - Files: `reference/cli-commands.md`

2. ✅ **Configuration Reference**
   - Hooks configuration
   - MCP server settings
   - Agent behavior
   - Files: `reference/configuration.md`

3. ✅ **Add executable examples everywhere**
   - Show command + expected output
   - Reduces cognitive load
   - Builds confidence

4. ✅ **Create Deep Dives section**
   - Context aggregation internals
   - Agent loop mechanics
   - Multi-session memory
   - Hooks system
   - Extended thinking
   - Files: `deep-dives/*.md`

**Success Criteria:**
- [ ] Every command shows expected output
- [ ] All configuration options documented
- [ ] Advanced users can find technical depth

---

### Phase 4: Quickstart & Onboarding (Week 4) 🚀

**Goal:** Fast path from install → first insight

**Deliverables:**
1. ✅ **5-minute quickstart**
   - Time commitment stated
   - Working example with real outcome
   - Expected output at each step
   - Success criteria defined
   - Files: `getting-started/quickstart.md`

2. ✅ **Enhanced Key Concepts**
   - Context aggregation
   - Agents & modes
   - Planning & iteration
   - @ Mentions
   - Hooks
   - Files: `getting-started/key-concepts.md`

3. ✅ **Navigation improvements**
   - Breadcrumbs
   - Sticky TOC for long pages
   - "Next steps" links
   - Clear hierarchy

**Success Criteria:**
- [ ] New user completes first analysis in <5 minutes
- [ ] Quickstart shows real outcome (not toy example)
- [ ] Clear path from Quickstart → Guides → Deep Dives

---

## 🎯 Success Metrics

### Engagement
- [ ] 80%+ of visitors view landing page (What is SignalPilot?)
- [ ] 60%+ view "How SignalPilot Works" architecture page
- [ ] 50%+ complete quickstart
- [ ] <10% bounce rate on landing page

### Clarity
- [ ] <5% support tickets asking "what is SignalPilot?"
- [ ] <5% confusion about CLI vs extension
- [ ] 90%+ understand "context orchestration" positioning (survey)

### Effectiveness
- [ ] <5 minutes average time-to-first-analysis
- [ ] 90%+ of users complete quickstart successfully
- [ ] Docs mentioned positively in user feedback

---

## 📝 Critical Files to Modify

### New Files to Create

1. **`introduction/what-is-signalpilot.md`**
   - Source: Aurora One Pager
   - Purpose: Context orchestration positioning
   - Priority: 🔴 CRITICAL

2. **`introduction/why-signalpilot.md`**
   - Source: Analysis above
   - Purpose: Comparison vs ChatGPT/Copilot
   - Priority: 🔴 CRITICAL

3. **`introduction/how-it-works.md`**
   - Source: Architecture diagram
   - Purpose: MCP + Agent Loop + Memory
   - Priority: 🔴 CRITICAL

4. **`getting-started/installation.md`**
   - Source: cli-docs.md (restructured)
   - Purpose: Installation guide (not product overview)
   - Priority: 🔴 CRITICAL

5. **`getting-started/quickstart.md`**
   - Source: New content
   - Purpose: 5-min outcome-focused tutorial
   - Priority: 🟡 HIGH

### Files to Restructure

1. **`new-doc-spec/cli-docs.md` → `getting-started/installation.md`**
   - Change: Reframe as installation guide
   - Clarify: Jupyter extension is product, CLI is installer
   - Priority: 🔴 CRITICAL

2. **`old-docs/overview/overview.md` → `introduction/what-is-signalpilot.md`**
   - Change: Replace "AI-powered extension" with "Context Orchestration Engine"
   - Add: Aurora One Pager positioning
   - Priority: 🔴 CRITICAL

3. **`old-docs/overview/security-and-privacy.md` → `introduction/security-and-privacy.md`**
   - Change: Add MCP architecture, scope control, SOC 2, audit trail
   - Expand: From short page to comprehensive trust page
   - Priority: 🟡 HIGH

### Files to Keep with Updates

1. **`old-docs/overview/concepts.md` → `getting-started/key-concepts.md`**
   - Add: MCP, memory, hooks
   - Expand: Mental models section

2. **`old-docs/tutorials/ai-agents-jupyter-2025.md`**
   - Add: Context about MCP, memory
   - Show: Not just code generation

3. **`old-docs/core/connecting-databases/*.md` → `integrations/databases/*.md`**
   - Add: "What context this provides" section
   - Reorganize: Popular vs More tiers

---

## 🚦 Next Steps

### Immediate Actions

1. **Review this plan** - Edit sections that need adjustment
2. **Prioritize phases** - Confirm Phase 1 (Week 1) is correct priority
3. **Assign owners** - Who writes what?
4. **Set timeline** - 4 weeks realistic?

### Questions for Discussion

1. **Quickstart example:** Should it be:
   - Stripe revenue analysis?
   - Internal data investigation example?
   - Generic time-series analysis?

2. **CLI naming:** Keep `uvx signalpilot` or introduce `sp` alias?

3. **Deep Dives section:** Should it be separate or under "Concepts"?

4. **MCP sidecar diagram:** Do we have an updated version or should I create one?

5. **SOC 2 status:** What's the current status to document?

---

## 📚 Reference Materials

### Internal Docs Reviewed
- ✅ [Aurora One Pager](new-doc-spec/Aurora One Pager.md) - Context orchestration positioning
- ✅ [Best-in-Class Research](new-doc-spec/Research - Best-in-Class Dev Tool Docs.md) - Pattern analysis
- ✅ [SignalPilot Documentation](new-doc-spec/SignalPilot Documentation.md) - Documentation project plan
- ✅ [cli-docs.md](new-doc-spec/cli-docs.md) - Current CLI docs (needs restructuring)
- ✅ All old-docs/ files - Current website content

### External Pattern Sources
- **uv** - Progressive disclosure, executable examples with output
- **Cursor** - AI-native positioning, task-based organization
- **Cline** - Control mechanisms before autonomy
- **Continue.dev** - MCP user control, provider taxonomy
- **Vercel AI SDK** - Foundations section, architecture clarity
- **LangChain** - Modular taxonomy, multiple discovery paths
- **Stripe** - Outcome-focused entry points, dual navigation

---

## ✏️ EDIT THIS PLAN

**Instructions:**
- Edit any section that needs adjustment
- Add comments/questions inline
- Mark sections as approved/rejected
- Add new priorities or concerns
- When ready, we'll proceed with implementation

**Status:** DRAFT - Ready for your review and edits
