# Thesis template

## Start your own Overleaf project

1. Download the ZIP for the version your course provides. If your course has
   not specified a version, use **Code → Download ZIP** on GitHub.
2. In Overleaf, choose **New Project → Upload Project** and upload the ZIP.
   This creates your own project. If Overleaf asks for the main document,
   choose `main.tex`. Use pdfLaTeX as the compiler and select **Recompile**.
3. Set your cover details in `main.tex`. The cover uses the supplied Ethel
   logo as an example. Set `\thesislogo` to your own PDF or leave it empty
   to omit the logo. The source artwork is `figures/ethel.svg`.
   Write your abstract in `front-matter/abstract.tex` and acknowledgements
   in `front-matter/acknowledgements.tex`.
4. Replace the sample citations in `chapters/background.tex` and the plot
   in `chapters/results.tex` with your own material.

## Organize your chapters

The sample outline follows a design-and-evaluation project. Adapt it to your
thesis. You can remove or combine the Design, Implementation, User study,
and Future Work parts if they do not fit. Use the appendix for supplementary
material referenced from the main text.

Use these ranges as drafting estimates. Follow your programme's requirements
for the overall length and adjust each part to the evidence it needs.

| Heading | What belongs there | Drafting estimate |
| --- | --- | --- |
| Section (`\section`) | A major topic or step in the chapter's argument, such as how you collected and analyzed your data. | About 1–3 pages |
| Subsection (`\subsection`) | One aspect of the section, such as how you prepared the data. | Several paragraphs, roughly ½–2 pages |
| Subsubsection (`\subsubsection`) | A focused detail that readers may need to find, such as how you handled missing observations. | About 1–3 paragraphs |

See the nested example in `chapters/methods.tex`. Subsubsections are
numbered in the text. To include them in the table of contents, change
`tocdepth` from 2 to 3 in `main.tex`. The page margins for the thesis text
are set there with `\newgeometry{margin=26mm}`.

## Plot data with TikZ and PGFPlots

Open `figures/example-trend.tex` to edit the example coordinates and axis
labels. For measured data, you can also upload a CSV with column headers
and replace the plot command with
`\addplot table[x=trial,y=response_ms,col sep=comma] {figures/results.csv};`.
Use a descriptive caption, label both axes, and include units where applicable.
Refer to the plot from the text with `Figure~\ref{fig:example-trend}`.

## Cite and manage sources

Add your records to `references.bib`. Use `\citet{key}` when the author is
part of the sentence and `\citep{key}` for a citation in parentheses. The
file includes examples for a journal article, an institutional web page,
and a book. Use a bare identifier in `doi` and a full address in `url`.
BibTeX generates the alphabetical reference list from the sources you cite.
Check your programme's required citation style before submission. If you are
updating an older Overleaf copy, use **Recompile from scratch** once to
regenerate the bibliography in the new style.

## Optional example for courses using Ethel

[Ethel](https://ai.ethz.ch/education/ai4edu/Ethel.html) is the ETH AI Center's
open-source research platform for AI-assisted teaching, learning, and
assessment. If your course permits it, one possible use is to ask for feedback
on whether a reader can identify the research question from your introduction.
Assess the feedback yourself and check any factual claims against your sources.

If your course or programme asks you to disclose AI assistance, follow its
instructions. The example in `examples/ai-assistance.tex` shows how to describe
the tool, the task, and what you checked yourself. Adapt it to your actual
use and uncomment the corresponding input in `main.tex` if the section belongs
in your submission.

## Maintainer workflow

For a cohort, share a ZIP from a tagged release or a specific commit so students
all start from the same version. In the linked Overleaf template project, use
the GitHub integration to pull updates and recompile before sharing a version.

To compile locally, run `latexmk -pdf main.tex` from the repository root. It runs
pdfLaTeX and BibTeX and produces `main.pdf`.
