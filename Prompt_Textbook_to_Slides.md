# Prompt: Textbook-to-Beamer-Slides Workflow

> Copy and paste this prompt into a new session. Upload your textbook PDF and a reference slide PDF (optional). Adjust the bracketed parameters to your needs.

---

## Phase 1: Setup

I have uploaded a textbook PDF: **[TEXTBOOK TITLE]** by **[AUTHOR]** ([EDITION], [PUBLISHER], [YEAR]).

Please do the following **setup tasks**:

1. **Split the textbook** into separate chapter PDFs, one per chapter. Use the table of contents to identify chapter boundaries. Save each chapter in its own directory named `Chapter_XX_Title/`.
2. **Create a `CLAUDE.md`** file at the root of the directory with:
   - Directory structure
   - Chapter summary table (chapter number, title, page count, math density, key topics)
   - PDF page offset (if book page numbers differ from PDF page numbers)
   - Any compilation instructions
3. **Create a `LEARNINGS.md`** file (initially empty) to record lessons learned during slide creation.

---

## Phase 2: Slide Creation (repeat for each chapter)

Now create Beamer LaTeX slides for **Chapter [N]: [TITLE]**.

### Style Requirements
- **Beamer LaTeX** with `\usetheme{default}`, no navigation symbols
- **Colored highlight boxes** using `tcolorbox`:
  - **Yellow** (`yellow!20`): definitions, important concepts
  - **Red** (`red!15`): key results, warnings, critical takeaways
  - **Green** (`green!10`): examples, positive notes
- **Font:** `lmodern` (Latin Modern sans-serif)
- **Slide numbers:** `N/total` format in bottom right
- **No images** — use text, math, tables, and TikZ diagrams only
- **Dense technical content** — these are for [AUDIENCE LEVEL, e.g., "junior/senior engineering students"], not general audiences

### Content Requirements
- Target **~[40-70] slides** (approximately **[2] hours** of study time)
- Cover all major sections, varying depth by importance
- Include **page references** to the original textbook on each slide (e.g., `[Norton, pp. 3--4]` in small gray text at the bottom)
- Include **key equations** with derivations where applicable
- Include **worked examples** from the text
- Include **tables** for reference data (units, conversion factors, classification schemes, etc.)
- Include a **summary slide** with numbered key concepts
- Include a **key definitions slide** for important terminology
- End with **self-check questions** (8-12 questions testing understanding)
- For sections where the slides are necessarily condensed, note the page range where more detail can be found

### Compilation
- Compile with `pdflatex` (two passes for correct slide numbers)
- Save the `.tex` source and compiled `.pdf` in the chapter directory
- Update `LEARNINGS.md` with any new insights from the process

### Reference Slides (if provided)
[If you have uploaded reference slides, add:] I have also uploaded reference slides in `Reference_Slides/`. Please match their visual style, density, and level of technical depth. The reference slides use [DESCRIBE: e.g., "4 slides per page, but you should create 1 slide per page"].

---

## Phase 3: Documentation Update

After completing slides for all chapters, update `CLAUDE.md` with:
- Final directory structure
- Slide counts per chapter
- Any cross-chapter references or dependencies
- Compilation instructions

---

## Optional Parameters

- **Math density override:** For chapters with heavy math, increase the equation-to-text ratio and use multi-frame derivations.
- **Slide count target:** Adjust based on chapter length — roughly 1 slide per 1-1.5 pages of textbook content, more for math-heavy sections.
- **Additional tools:** If you need any software tools (e.g., Python scripts for processing), create them in the project directory.
