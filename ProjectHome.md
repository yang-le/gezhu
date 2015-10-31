This project hosts gezhu.sty, a TeX/LaTeX macro package to typeset gezhu. Gezhu (割注, literally Splitted Annotation; Warichu in Japanese) is a typesetting formula used in ancient Chinese books, where annotations are inserted into the main text in small fonts in two (or more) lines. The package gezhu.sty enables user to typeset gezhu of any length and any lines in a simplest form of input.

An example of gezhu usage is as follows.
```
\documentclass[12pt]{article}
\ifdefined\XeTeXrevision
  \usepackage{zhspacing}
  \zhspacing
  \XeTeXinputencoding "cp936"
\else
  \usepackage{CJK, CJKpunct}
  \AtBeginDocument{\begin{CJK*}{GBK}{song}}
  \AtEndDocument{\clearpage\end{CJK*}}
\fi
\usepackage{gezhu}
\setgezhulines{2}
\everygezhu{\fontsize{6}{7}\selectfont}
\setgezhuraise{-1.5pt}
\begin{document}
\fbox{\parbox{6.5em}{
\begin{withgezhu}
	这是割注\gezhu{在正文中插入的双行或多行注解}排版测试。
\end{withgezhu}}}
\end{document}
```