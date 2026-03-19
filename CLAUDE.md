# CLAUDE.md — Context for Future Sessions

## Project Overview

This directory contains **Design of Machinery** by Robert L. Norton (6th Edition, McGraw-Hill, 2020). The original textbook PDF (897 pages) has been split into 16 separate chapter PDFs, each in its own directory.

## Directory Structure

```
design_of_machinery/
├── CLAUDE.md                          ← this file
├── LEARNINGS.md                       ← lessons learned during slide creation
├── Reference_Slides/
│   └── lec4_2019.pdf                  ← reference Beamer slides (LQ Optimal Control, 43 slides, 4-per-page)
├── Chapter_01_Introduction/
│   ├── Chapter_01_Introduction.pdf    ← textbook chapter (27 pages)
│   ├── Chapter_01_Introduction_Slides.tex  ← Beamer LaTeX source
│   └── Chapter_01_Introduction_Slides.pdf  ← compiled slides (42 slides)
├── Chapter_02_Kinematics_Fundamentals/
│   ├── Chapter_02_Kinematics_Fundamentals.pdf
│   ├── Chapter_02_Kinematics_Fundamentals_Slides.tex  ← Beamer LaTeX source
│   └── Chapter_02_Kinematics_Fundamentals_Slides.pdf  ← compiled slides (38 slides)
├── Chapter_03_Graphical_Linkage_Synthesis/
│   ├── Chapter_03_Graphical_Linkage_Synthesis.pdf
│   ├── Chapter_03_Graphical_Linkage_Synthesis_Slides.tex  ← Beamer LaTeX source
│   └── Chapter_03_Graphical_Linkage_Synthesis_Slides.pdf  ← compiled slides (29 slides)
├── ... (through Chapter 16)
└── (original textbook PDF)
```

## Slide Creation Approach

### Style (matching Reference_Slides)
- **Beamer LaTeX** with default theme, no navigation symbols
- **Colored boxes** via `tcolorbox`: yellow (definitions), red (key results/warnings), green (examples)
- **Dense technical content** — these are for engineering students, not general audiences
- **Slide numbers** as `N/total` in bottom right
- **No images** — text, math, tables, and TikZ diagrams only
- **Font:** lmodern (Latin Modern sans-serif)

### Content Guidelines
- Target **~40-70 slides per chapter** depending on chapter length and density
- Target **~2 hours of study time** per chapter slide deck
- Cover all major sections but vary depth by importance
- Include **self-check questions** on the final slide
- Include **worked examples** and **key equations** with derivations where applicable
- Use **tables** for unit systems, conversion factors, and comparative data
- The later chapters (4-9, 10-16) are much more math-heavy and will need more equation slides

### Compilation
- Compile with `pdflatex` (two passes for correct slide numbers)
- All required packages are available in the system TeX Live installation
- No external images needed; diagrams created with TikZ

## Chapter Content Summary

| Ch | Title | Pages | Math Density | Key Topics |
|----|-------|-------|-------------|------------|
| 1 | Introduction | 27 | Low | Design process, kinematics vs kinetics, units |
| 2 | Kinematics Fundamentals | 68 | Medium | DOF, Grashof, linkage classification, mobility |
| 3 | Graphical Linkage Synthesis | 80 | Medium | 2/3-position synthesis, cognates, straight-line |
| 4 | Position Analysis | 55 | High | Vector loop equations, numerical methods |
| 5 | Analytical Linkage Synthesis | 58 | High | Precision points, Burmester theory |
| 6 | Velocity Analysis | 66 | High | Instant centers, velocity polygons |
| 7 | Acceleration Analysis | 52 | High | Coriolis, acceleration polygons |
| 8 | Cam Design | 81 | High | SVAJ diagrams, pressure angle, cam profiles |
| 9 | Gear Trains | 63 | Medium-High | Involute profiles, epicyclic trains |
| 10 | Dynamics Fundamentals | 36 | High | Lumped parameters, energy methods |
| 11 | Dynamic Force Analysis | 53 | High | Matrix methods, shaking forces |
| 12 | Balancing | 30 | High | Static/dynamic balance, field balancing |
| 13 | Engine Dynamics | 45 | High | Slider-crank, gas forces, flywheels |
| 14 | Multicylinder Engines | 46 | High | Firing order, Vee engines |
| 15 | Cam Dynamics | 32 | High | Follower dynamics, resonance |
| 16 | Cam- and Servo-Driven Mechanisms | 22 | Medium-High | Servomotors, combined mechanisms |

## PDF Page Offset

The original textbook has a page offset of **27** between PDF page numbers and book page numbers:
- Book page N → PDF page N + 27
- Example: Book page 3 (Chapter 1 start) → PDF page 30

## Important Notes

- The textbook is copyrighted by McGraw-Hill Education (2020). Slides are for personal study use.
- Chapter 1 is primarily conceptual; Chapters 2+ become increasingly mathematical.
- The reference slides are from a control theory course — the style transfers well to mechanism design content since both are technical engineering subjects.
- When creating slides for later chapters, expect to need significantly more equation-heavy slides with derivations spanning multiple frames.
