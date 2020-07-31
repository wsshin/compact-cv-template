# compact-cv-template
LaTeX template to create a compact curriculum vitae (CV) such as [http://www.mit.edu/~wsshin/pdf/shin_cv.pdf](http://www.mit.edu/~wsshin/pdf/shin_cv.pdf).  

## How to use
1. Put `cv.tex`, `cv_geoemtry.tex`, `cv_biblatex_format.tex` in the same directory.  
2. Change the followings in `cv.tex`:
- Definitions (`\def`) in "Personal information" section
- Main contents within `\begin{document} ... \end{document}`
3. Additionally, if you want to include your publications, you need to provide your own `publications.bib` file (see below for additional information).
4. Finally, use `pdflatex` to process the `*.tex` files and produce `cv.pdf`.

## About `publications.bib`
The template generates multiple publication lists automatically out of the BibTeX file `publications.bib`.
- The publications are automatically sorted in the reverse chronological order.  If you have 10 publications, the first publication in the list is the most recent publication and numbered 10, and the next publication in the list is the second-most recent publication and numbered 9, etc.
- In each bibliography item in `publications.bib`, add a new field named `Entrysubtype`.  (If you use BibDesk on macOS, this can be done by BibDesk > Publication > Add Field...)  This field is used to show only the bibliography items with a specific `Entrysubtype` value.  For example, put `oral` as the value of `Entrysubtype` for oral presentations in conferences, and use `\printbibliography[subtype=oral]` to show only the bibliography items tagged `oral` in `Entrysubtype`.  See more examples in `\section{Refereed Journal Publications}`, `\section{Conference Oral Presentations}`, `\section{Conference Poster Presentations}` in `cv.tex`.
- The specific format in which each publication is shown is defined in `cv_biblatex_format.tex`, which you need to change in order to use a different format.

## Special instruction for creating the contents within `\begin{document} ... \end{document}`
In each section, the first subsection title needs to be defined in `\subsectionone{...}` for a formatting reason.  The remaining subsection titles need to be defined in the usual `\subsection{...}`.  A pull request to eliminate the need for the special subsection command for first subsections is welcome.

## About fonts
I personally use the Minion Pro font, because it is a relatively narrow-width font and therefore I can put more contents with it.  The Minion Pro font is proprietary and comes with Adobe Acrobat.  If you have Adobe Acrobat, you can use it in LaTeX by installing the [`minionpro` package](https://ctan.org/pkg/minionpro?lang=en).  The installation of the `minionpro` package, however, is not straightforward.
