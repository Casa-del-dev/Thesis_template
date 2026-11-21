# Thesis template

## Start in Overleaf

1. Download the ZIP your course provides, or choose **Code → Download ZIP**
   on GitHub.
2. In Overleaf, select **New Project → Upload Project** and upload the ZIP.
   If prompted, select `main.tex` as the main document and pdfLaTeX as the
   compiler.
3. Compile once and skim the PDF. The text under each heading explains what
   a research reader expects and gives a starting length where useful.
   Replace those passages with your own writing as you draft.

## Where to work

| File or folder | What to edit |
| --- | --- |
| `main.tex` | Set your cover details and choose which chapters to include. Replace the example Ethel logo via `\thesislogo`, or leave that field empty. |
| `front-matter/` | Write your abstract and acknowledgements. Acknowledgements come before the optional table of contents. The abstract follows. |
| `chapters/` | Draft your thesis one chapter at a time. Use the Methods file for an example of numbered headings. |
| `references.bib` | Add your sources and replace the example citations in Related Work. |
| `figures/` | Store images and edit the sample PGFPlots chart. The original Ethel artwork is `figures/ethel.svg`. |
| `examples/` | Find the two table examples used in Results. |

The table of contents is enabled by default. If your programme does not
require it, comment out `\tableofcontents` in `main.tex`.

## While drafting

**Structure.** Open a section with a short paragraph explaining its purpose
and what the subsections will cover. Use a subsection when two or more distinct topics each need
their own explanation and heading. Keep the hierarchy shallow and avoid
subsubsections by default. The sample outline fits a design-and-evaluation
project. Combine or remove chapters and sections that your research does
not need.

**Tables.** Start with `examples/tables.tex`. Use `tabular` for short columns
and `tabularx` with an `X` column for text that needs to wrap. The examples
use `&` to separate cells and `\\` to end rows. Give each table a caption,
put its `\label` after the caption, and cite it in the text with
`Table~\ref{tab:example-values}`. Replace the examples or remove the
`\input{examples/tables}` line in `chapters/results.tex`.

**Images.** The Design chapter shows how to include a PDF with
`\includegraphics`, a caption, and a cross-reference. At the size the
image appears on the page, aim for labels at least as large as the caption.

**Plots.** Edit the coordinates and axis labels in `figures/example-trend.tex`.
To load measured data, upload a CSV with headers and replace the plot command
with `\addplot table[x=trial,y=response_ms,col sep=comma] {figures/results.csv};`.
Use readable axis labels and units.

**Citations.** Add sources to `references.bib` and cite them with
`\cite{key}`. This prints a bracketed number such as [1], which links to the
matching numbered entry in References. Use `\cite{key1,key2}` to group sources.
The bibliography includes the sources cited in the text. Use **Recompile from
scratch** if an older Overleaf copy still shows stale citations.

**Draft feedback.** Use `\todo{Check fit.}` in the margin and
`\todo[inline]{Check the analysis description.}` for a longer note.
The Methods chapter demonstrates `\gerd{...}` and `\stefan{...}` for named
reviewer comments. Copy a reviewer definition in `main.tex` to add another
reviewer. Uncomment `\listoftodos` to collect feedback in a single list.

## Before submitting

- Replace the writing guidance, sample figures and tables, and example
  citations. Check your programme's requirements for layout and declarations.
- Resolve reviewer comments and uncomment
  `\PassOptionsToPackage{disable}{todonotes}` in `main.tex` to hide draft
  notes and the checklist. Compile and read through the final PDF.
- Follow your programme's guidance on disclosing AI assistance.

## Maintain the template

Share a ZIP from a specific release or commit so the cohort starts with the
same files. In the linked Overleaf project, pull GitHub changes and recompile
before sharing. Overleaf needs only the source files and supporting assets.
For local builds, use `latexmk -pdf -outdir=/tmp/thesis-build main.tex` to keep
the PDF and generated files outside the checkout.
