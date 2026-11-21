# Thesis template

## Start your own Overleaf project

1. Download the ZIP for the version your course provides. If your course has
   not specified a version, use **Code → Download ZIP** on GitHub.
2. In Overleaf, choose **New Project → Upload Project** and upload the ZIP.
   This creates your own project. If Overleaf asks for the main document,
   choose `main.tex`. Use pdfLaTeX as the compiler and select **Recompile**.
3. Fill in the five title-page fields near the top of `main.tex`. Write your
   abstract there and draft each chapter in `chapters/`.
4. Add your sources to `references.bib`. Replace the sample citation in
   `chapters/background.tex` and remove its sample bibliography entry when
   you no longer need it. Use `\cite{key}` to cite an entry.

Check your programme's instructions for the required title page, chapter
structure, citation style, and declarations before submitting.

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
