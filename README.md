# compact-cv-template
This is a LaTeX template to create a compact curriculum vitae (CV) such as the one shown at [http://www.mit.edu/~wsshin/pdf/shin_cv.pdf](http://www.mit.edu/~wsshin/pdf/shin_cv.pdf).  

## What you need to change
- Definitions (`\def`) in "Personal information" section
- Main contents within `\begin{document} ... \end{document}`
- If you want to include your publications, `publications.bib` file

## About `publications.bib`
I made a great effort to list publications automatically out of a BibTeX file.
- The format in which each publication is shown is defined in `cv_biblatex_format.tex`, which you need to change in order to use a different format.
- The publications are automatically sorted in the reverse chronological order.  If you have 10 publications, the first publication in the list is the most recent publication and numbered 10, and the next publication in the list is the second-most recent publication and number 9, etc.
- In each bibliography item in `publications.bib`, add a new field named `Entrysubtype`.  (If you use BibDesk on macOS, this can be done by BibDesk > Publication > Add Field...)  This field is used to show only the bibliography items with a specific `Entrysubtype` value.  For example, put `oral` as the value of `Entrysubtype` for oral presentations in conferences, and use `\printbibliography[subtype=oral]` to show only the bibliography items tagged `oral` in `Entrysubtype`.  See more examples in `\section{Refereed Journal Publications}`, `\section{Conference Oral Presentations}`, `\section{Conference Poster Presentations}`

## Special instruction for creating the contents within `\begin{document} ... \end{document}`
In each section, the first subsection title needs to be defined in `\subsectionone{...}` for a formatting reason.  The remaining subsection titles need to be defined in the usual `\subsection{...}`.  A pull request to eliminate the need for the special subsection command for first subsections is welcome.

## About fonts
I personally use the Minion Pro font, because it is a relatively narrow-width font and therefore I can put more contents with it.  Howevwer, the Minion Pro font is proprietary (even though it comes with Adobe Acrobat).  Even if you have Adobe Acrobat, you need to install the `minionpro` package (https://ctan.org/pkg/minionpro?lang=en), which I found tricky.
