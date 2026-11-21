# Thesis template

Edit the title, author, and date in `main.tex`. Draft each chapter in
`chapters/`. Add sources to `references.bib` and cite them with
`\cite{key}`. Replace the sample citation and its bibliography entry
when you add your own sources.

## Compile in Overleaf

Set the main document to `main.tex` and the compiler to pdfLaTeX.
If this repository is already linked to your Overleaf project, open
the project's GitHub integration and pull the latest changes.

## Compile locally

Run `latexmk -pdf main.tex` from the repository root. This runs
pdfLaTeX and BibTeX and produces `main.pdf`.
