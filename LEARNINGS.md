# LEARNINGS.md — Lessons Learned Creating Beamer Slides from Textbook Chapters

## LaTeX / Beamer Workflow

1. **pdflatex is available** on this system along with xelatex and lualatex. Beamer class (`beamer.cls`) is installed via TeX Live 2022. No additional package installation was needed.

2. **Two compilation passes** are needed for Beamer to get correct slide numbers (`N/total` format) and any cross-references. The first pass generates `.aux` files; the second resolves them.

3. **tcolorbox** is the best package for creating the colored highlight boxes seen in the reference slides. Using `colback` and `colframe` set to the same color with `boxrule=0pt` produces frameless colored boxes that match the reference style perfectly.

4. **Matching the reference style** required:
   - `\usetheme{default}` with `\usecolortheme{default}` — no fancy Beamer themes
   - Navigation symbols removed: `\setbeamertemplate{navigation symbols}{}`
   - Custom footline showing only `N/total` page numbers
   - `lmodern` font package for clean sans-serif text
   - Three box types: `yellowbox` (definitions), `redbox` (warnings/key results), `greenbox` (examples)

5. **TikZ diagrams** work well within Beamer frames for flowcharts and process diagrams. Use `node distance`, `rounded corners`, and fill colors for clean results. Keep diagrams simple — complex TikZ can cause overfull vbox warnings.

6. **Overfull vbox warnings** are common in Beamer when slides have too much content. These are cosmetic warnings (content may be slightly clipped at the bottom). Solutions: reduce content, decrease font size locally with `\small`, or split across two frames.

## Content Strategy for Textbook-to-Slides Conversion

7. **Not every section needs equal coverage.** The design process (Section 1.5) warranted ~12 slides because it's the pedagogical core. The bibliography (Section 1.15) was omitted entirely. History got 2 slides. Units got 6 slides because of the critical fps/ips/SI distinctions.

8. **Self-check questions** on the final slide are valuable — they help students gauge their understanding and are common in university lecture slides.

9. **Tables from the textbook** translate well to Beamer using `booktabs` package (`\toprule`, `\midrule`, `\bottomrule`). Use `\small` or `\footnotesize` for larger tables to fit them on a single slide.

10. **The case study** (Towfigh's fourbar linkage) provides a narrative thread that ties the creative process concepts together. Including it gives the slides a concrete, memorable example rather than just abstract theory.

11. **42 slides** for an introductory chapter is a good target for ~2 hours of study time (approximately 3 minutes per slide for reading, understanding, and note-taking).

## Chapter 2 Specific Learnings

13. **Chapter 2 is significantly more technical than Chapter 1.** It required more equation slides (Gruebler, Kutzbach, Grashof, N-bar rotatability) and classification tables (Barker's 14 types, six lower pairs, isomer counts). At 38 slides covering 68 pages, the density is roughly 1 slide per 1.8 textbook pages — tighter than Chapter 1's 1:0.64 ratio because of the conceptual depth per page.

14. **Classification tables are essential reference material.** Barker's 14-type classification, the six lower pairs, and the number synthesis results table are the kind of content students will want to return to repeatedly. These are best presented as compact tables with `\scriptsize` or `\small` font.

15. **The `\pref{}` command** for page references works well as a reusable macro. Defined once in the preamble as `\newcommand{\pref}[1]{\vfill\hfill{\scriptsize\color{gray}[Norton, pp.~#1]}}`, it consistently places a gray reference at the bottom-right of each slide. For future chapters, the "Norton" prefix in the macro could be parameterized.

16. **Comparison tables** (linkages vs. cams) are highly effective for practical design guidance. Students appreciate seeing trade-offs laid out side by side rather than buried in prose.

17. **Motors/drivers section** (2.19) is long in the textbook but was condensed to 3 slides since the detailed torque-speed curves are better understood from the figures in the text. The slides focus on the classification and selection criteria rather than reproducing the curves.

## Chapter 3 Specific Learnings

18. **Chapter 3 is heavily procedural** — the core content is step-by-step graphical construction methods (Examples 3-1 through 3-10). The slides must distill these multi-step procedures into concise summaries rather than reproducing every step, since the constructions are inherently visual and best learned by doing them with compass and straightedge. Page references are critical here so students can follow the full procedure in the text.

19. **The chapter has a natural "build" structure**: 2-position → 3-position → specified pivots → quick-return → coupler curves → cognates → straight-line → dwell. Each section builds on the previous. The slides follow this order faithfully.

20. **Coupler curves section** is the richest for conceptual content (cusps, crunodes, the H&N atlas, symmetrical linkages, degree of curves). This deserved 3 slides despite being only ~10 textbook pages, because the concepts are dense and students need to understand the design space.

21. **At 29 slides for 80 textbook pages**, Chapter 3 has the lowest slide-per-page ratio so far (~0.36). This is appropriate because much of the chapter is worked examples with geometric constructions that don't translate well to text-only slides. The slides focus on concepts, methods, and key results rather than reproducing constructions.

22. **Roberts' theorem and cognates** are a highlight that students often find surprising and elegant. Worth giving full emphasis — the practical implication (relocating fixed pivots) is a powerful design tool.

## Reference Slides Analysis

12. **The reference slides** (lec4_2019.pdf on LQ Optimal Control) have 43 slides with 4 per page in the PDF (handout mode). Key style elements:
    - Very dense mathematical content with full derivations
    - Yellow boxes for definitions and setup
    - Red/pink boxes for key results and theorems
    - Code examples (MATLAB) shown in monospace
    - Proofs shown step-by-step across multiple slides
    - No images or decorations — purely text and math
    - Slide numbers in format `N/total` at bottom right
