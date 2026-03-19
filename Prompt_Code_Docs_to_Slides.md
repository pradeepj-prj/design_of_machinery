# Prompt: Code Documentation / Library-to-Beamer-Slides Workflow

> Copy and paste this prompt into a new session. Provide the library documentation (PDF, URL, or uploaded files). Adjust the bracketed parameters to your needs.

---

## Phase 1: Autonomous Research and Chapter Breakdown

I want to create a comprehensive Beamer slide deck for the **[LIBRARY/FRAMEWORK NAME]** library (e.g., LangChain, LangGraph, FastAPI, React, PyTorch).

**Documentation source:** [Upload PDFs / provide URLs / describe what you have]

**I am not deeply familiar with this library.** I need you to independently research the library and propose a complete chapter/section breakdown. Do NOT ask me what sections to create — figure it out yourself by analyzing the documentation, source code, and your own knowledge.

Please do the following **setup tasks**:

1. **Deep-dive into the library.** Read the uploaded docs, fetch the official documentation site, and/or use your training knowledge to build a thorough understanding of the library's architecture, key modules, common usage patterns, and ecosystem.

2. **Autonomously design a chapter breakdown.** Based on your research, propose a logical sequence of sections that a learner would follow from zero knowledge to proficiency. Follow these principles:
   - **Start with "why"** — the first section should motivate why this library exists and what problems it solves, before any API details.
   - **Build incrementally** — each section should build on the previous one. A reader should never encounter a concept that depends on something not yet covered.
   - **Group by mental model, not by API surface** — organize around what the user is trying to accomplish (e.g., "Building Chains" not "The Chain Class"), since learners think in tasks, not in class hierarchies.
   - **Separate core from advanced** — put the 20% of the library that covers 80% of use cases up front. Push niche/advanced topics to later sections.
   - **Include a "Putting It All Together" section** — a near-final section that walks through building a realistic, non-trivial project using everything covered so far.

3. **Present the proposed breakdown as a table** before creating any slides:

   | Section | Title | Prerequisites | Key Concepts | Est. Slides | Study Time |
   |---------|-------|---------------|--------------|-------------|------------|
   | 00 | Overview & Architecture | None | ... | 15-20 | 30 min |
   | 01 | Core Concepts | 00 | ... | 40-50 | 1.5 hr |
   | ... | ... | ... | ... | ... | ... |
   | 99 | Quick Reference | All | ... | 10-15 | — |

   For each section, briefly justify why it exists and why it's in that position in the sequence. Flag any sections where the ordering is debatable and explain the trade-off.

4. **Wait for my approval** of the chapter breakdown before proceeding. I may ask you to merge, split, reorder, or drop sections. Once I approve, proceed to Phase 2.

5. **Create a `CLAUDE.md`** file with the directory structure and project overview.
6. **Create a `LEARNINGS.md`** file to track lessons learned.

---

## Phase 2: Slide Creation (repeat for each section)

Now create Beamer LaTeX slides for **Section [N]: [TITLE]**.

### Style Requirements
- **Beamer LaTeX** with `\usetheme{default}`, no navigation symbols
- **Colored highlight boxes** using `tcolorbox`:
  - **Yellow** (`yellow!20`): key concepts, API definitions, important interfaces
  - **Red** (`red!15`): common pitfalls, breaking changes, critical warnings, performance gotchas
  - **Green** (`green!10`): best practices, tips, recommended patterns
  - **Blue** (`blue!10`): code examples and snippets (use `\texttt{}` or `lstlisting`)
- **Font:** `lmodern` (Latin Modern sans-serif)
- **Slide numbers:** `N/total` format in bottom right
- **No images/screenshots** — use text, code listings, TikZ architecture diagrams, and tables only
- **Code snippets** should use `lstlisting` or `verbatim` environments with syntax highlighting where possible

### Content Requirements
- Target **~[30-60] slides per section** (approximately **[1-2] hours** of study time per section)
- **For each major concept, include:**
  1. **What it is** (definition/purpose slide)
  2. **Why it matters** (motivation/use case slide)
  3. **How to use it** (code example slide with minimal working example)
  4. **Common patterns** (idiomatic usage, best practices)
  5. **Gotchas** (common mistakes, edge cases, performance issues)
- Include **architecture diagrams** using TikZ (e.g., data flow, component relationships, request lifecycle)
- Include **comparison tables** where relevant (e.g., "When to use X vs Y", "Sync vs Async", "v1 vs v2 API changes")
- Include **reference to documentation** sections/URLs on each slide (e.g., `[Docs: langchain.com/docs/modules/chains]` in small gray text)
- Include a **"Mental Model" slide** at the start of each section showing how the concepts fit together
- End each section with:
  - **Summary slide** with key takeaways
  - **Cheat sheet slide** with the most-used API calls / patterns
  - **Self-check questions** testing understanding (5-8 questions)

### Code Example Guidelines
- Keep examples **minimal but complete** — a reader should be able to copy-paste and run them
- Show **imports** explicitly (don't assume the reader knows which module things come from)
- Use **comments** to explain non-obvious lines
- When showing a pattern, show both the **basic version** and the **production-ready version** on successive slides
- For complex flows, build up the code **incrementally** across multiple slides

### Architecture Diagrams (TikZ)
- Use TikZ for all diagrams: data flow, component relationships, class hierarchies, request/response cycles
- Keep diagrams **simple and readable** — max 8-10 nodes per diagram
- Use consistent color coding: yellow for data/state, green for processing, red for I/O, blue for external services
- Label all arrows with the data or action being passed

### Version-Specific Notes
- Library version: **[VERSION, e.g., "v0.3.x"]**
- If the API has changed significantly between versions, note the differences on relevant slides
- Mark any deprecated features clearly in red boxes

---

## Phase 3: Cross-Cutting Slides

After the per-section slides, create these additional slide decks:

1. **`00_Overview_and_Architecture.tex`** — High-level overview of the entire library: what it does, when to use it, how the pieces fit together. Include a "big picture" TikZ diagram.

2. **`99_Quick_Reference.tex`** — A condensed cheat sheet (10-15 slides max) with:
   - Most common import statements
   - Key class/function signatures
   - Common patterns in compact form
   - Troubleshooting checklist

---

## Phase 4: Compilation and Documentation

- Compile all `.tex` files with `pdflatex` (two passes each)
- Update `CLAUDE.md` with final structure, slide counts, and version info
- Update `LEARNINGS.md` with insights about the library and slide creation process

---

## Directory Structure

```
[library_name]_slides/
├── CLAUDE.md
├── LEARNINGS.md
├── 00_Overview_and_Architecture/
│   ├── 00_Overview_and_Architecture.tex
│   └── 00_Overview_and_Architecture.pdf
├── 01_Core_Concepts/
│   ├── 01_Core_Concepts.tex
│   └── 01_Core_Concepts.pdf
├── 02_Getting_Started/
│   └── ...
├── ...
└── 99_Quick_Reference/
    ├── 99_Quick_Reference.tex
    └── 99_Quick_Reference.pdf
```

---

## Optional Parameters

- **Audience level:** [beginner / intermediate / advanced] — adjusts the ratio of conceptual vs. advanced content
- **Focus area:** If you only care about certain parts of the library (e.g., "only the Agents and Tools modules in LangChain"), specify here
- **Comparison with alternatives:** If you want slides comparing this library to alternatives (e.g., LangChain vs LlamaIndex), add a comparison section
- **Integration examples:** If you want slides showing integration with specific tools (e.g., "LangChain + PostgreSQL + FastAPI"), specify here
