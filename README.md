# Design of Machinery — Study Slides

Beamer LaTeX lecture slides for **Design of Machinery** by Robert L. Norton (6th Edition, McGraw-Hill, 2020). Created for personal study use.

## What's Here

The original textbook has been split into 16 chapter PDFs. For each chapter with completed slides, the directory contains the chapter PDF, a `.tex` source file, and a compiled `.pdf` slide deck.

| Ch | Title | Pages | Slides | Status |
|----|-------|-------|--------|--------|
| 1 | Introduction | 27 | 42 | Done |
| 2 | Kinematics Fundamentals | 68 | 38 | Done |
| 3 | Graphical Linkage Synthesis | 80 | 29 | Done |
| 4 | Position Analysis | 55 | — | Chapter PDF only |
| 5 | Analytical Linkage Synthesis | 58 | — | Chapter PDF only |
| 6 | Velocity Analysis | 66 | — | Chapter PDF only |
| 7 | Acceleration Analysis | 52 | — | Chapter PDF only |
| 8 | Cam Design | 81 | — | Chapter PDF only |
| 9 | Gear Trains | 63 | — | Chapter PDF only |
| 10 | Dynamics Fundamentals | 36 | — | Chapter PDF only |
| 11 | Dynamic Force Analysis | 53 | — | Chapter PDF only |
| 12 | Balancing | 30 | — | Chapter PDF only |
| 13 | Engine Dynamics | 45 | — | Chapter PDF only |
| 14 | Multicylinder Engines | 46 | — | Chapter PDF only |
| 15 | Cam Dynamics | 32 | — | Chapter PDF only |
| 16 | Cam- and Servo-Driven Mechanisms | 22 | — | Chapter PDF only |

## Slide Style

The slides are modeled after a set of control-theory reference slides (included in `Reference_Slides/`) and use a consistent Beamer style:

- **Default Beamer theme** with no navigation symbols
- **Colored highlight boxes** via `tcolorbox`: yellow (definitions), red (key results/warnings), green (examples)
- **Page references** on every slide pointing back to the textbook (e.g., `[Norton, pp. 30–31]`)
- **Self-check questions** at the end of each deck
- **No images** — all content is text, math, tables, and TikZ diagrams
- **Target:** ~2 hours of study time per chapter deck

## Building the Slides

Requires a TeX Live installation with Beamer. Compile with two passes for correct slide numbering:

```bash
cd Chapter_01_Introduction
pdflatex Chapter_01_Introduction_Slides.tex
pdflatex Chapter_01_Introduction_Slides.tex
```

## Other Files

- `CLAUDE.md` — Project context for AI-assisted continuation of slide creation
- `LEARNINGS.md` — Lessons learned during the slide creation process
- `Prompt_Textbook_to_Slides.md` — Reusable prompt template for converting any textbook into Beamer slides
- `Prompt_Code_Docs_to_Slides.md` — Reusable prompt template for converting code library documentation into Beamer slides
