# P1 JTT Anonymous Manuscript LaTeX

This folder contains the anonymous JTT manuscript in editable LaTeX. It was converted from the 1 October 2026 Word submission version and includes the four figures used in the main text.

## Files

- `P1_JTT_Anonymous_Manuscript.tex`: complete anonymous manuscript, tables, legal instruments and references.
- `figures/`: the four main-text figures, with descriptive filenames.
- `P1_JTT_Anonymous_Manuscript.pdf`: compiled preview.

## Build

Run from this folder:

```powershell
xelatex -interaction=nonstopmode -halt-on-error P1_JTT_Anonymous_Manuscript.tex
xelatex -interaction=nonstopmode -halt-on-error P1_JTT_Anonymous_Manuscript.tex
```

The source uses Times New Roman and requires XeLaTeX. References are included directly in the `.tex` file, so BibTeX and external bibliography files are not required. Keep the separate JTT title page and cover letter outside the anonymous manuscript upload.
