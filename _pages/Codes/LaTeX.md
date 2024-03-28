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