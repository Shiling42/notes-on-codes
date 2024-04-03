---
author: Shing Liang
category: Jekyll
layout: post
mermaid: true
---

## Math
### reaction arrows

````LaTeX
\underset{k_b}{\stackrel{k_f}{\rightleftharpoons}}

### Clockwised arrow
```LaTeX
\frac{\prod_\circlearrowright W_{ij}}{\prod_\circlearrowleft W_{ji}}
```
````
## General
### Color text
```LaTeX
\usepackage{xcolor}
\color{red}{}
```

### Switch to single column appendix
```LaTeX
\onecolumn
\appendix
\numberwithin{equation}{section}
\numberwithin{figure}{section}
```

## Figures
### Basic figure
```LaTeX
\begin{figure}
\centering
\includegraphics[width=.9\columnwidth]{*}
\caption{}
\label{fig:*}
\end{figure}
```
### Subfigure
```LaTeX
\begin{figure}
    \centering
    \begin{subfigure}[b]{.8\columnwidth}
        \includegraphics[width=\linewidth]{}
        \caption{}
        \label{fig:a}
    \end{subfigure}
    \begin{subfigure}[b]{.49\columnwidth}
        \includegraphics[width=1\linewidth]{}
        \caption{}
    \end{subfigure}
    \caption{} 
    \label{fig:1}
\end{figure}
```

## Templates
### Paper for notes (compact)
```LaTeX
\documentclass[11pt,floatfix,twocolumn]{paper}

%\linespread{1.5}
\usepackage[margin=1.in]{geometry}

\usepackage{bm}
\usepackage{color}

\usepackage{amsmath,amsfonts,amsthm,amssymb,appendix,xcolor,comment,mathtools,braket,empheq,hyperref,graphicx}

```
### Revetex (with Chinese name)
```LaTeX
\documentclass[aps,reprint,amsmath,amssymb,groupaddress,superscriptaddress,prl]{revtex4-2}

\usepackage{amsmath, amsfonts, amssymb, bm, color, graphicx, soul, hyperref, CJK, xcolor, mathtools, lipsum}

\begin{document}
\begin{CJK*}{UTF8}{gbsn}

\title{}
\author{Shiling Liang (梁师翎)}
\email{shiling.liang@epfl.ch}
\affiliation{}

\begin{abstract}
\end{abstract}
\end{CJK*}
\begin{document}
```