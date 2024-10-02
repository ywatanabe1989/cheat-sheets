# LaTeX Cheat Sheet

## Basic Document Structure
```tex
\documentclass{article}
\usepackage{packages}

\begin{document}
    Your content here
\end{document}
```

## Text Formatting
- Bold: `\textbf{text}`
- Italic: `\textit{text}`
- Underline: `\underline{text}`

## Sections
- `\section{Title}`
- `\subsection{Subtitle}`
- `\subsubsection{Subsubtitle}`

## Lists
### Unordered List
```tex
\begin{itemize}
    \item First item
    \item Second item
\end{itemize}
```

### Ordered List
```tex
\begin{enumerate}
    \item First item
    \item Second item
\end{enumerate}
```

## Math Mode
- Inline math: `$equation$`
- Display math: 
```tex
\[
    equation
\]
```

### Common Mathematical Symbols and Notations

| Symbol | LaTeX Code | Symbol | LaTeX Code |
|--------|------------|--------|------------|
| ≤      | `$\leq$`   | ≥      | `$\geq$`   |
| ≠      | `$\neq$`   | ≈      | `$\approx$`|
| ±      | `$\pm$`    | ×      | `$\times$` |
| ÷      | `$\div$`   | ∑      | `$\sum$`   |
| ∏      | `$\prod$`  | ∫      | `$\int$`   |
| ∞      | `$\infty$` | √      | `$\sqrt{}$`|
| ∂      | `$\partial$`| ⊂     | `$\subset$`|
| ∈      | `$\in$`    | ∪      | `$\cup$`   |
| ∩      | `$\cap$`   | α      | `$\alpha$` |
| β      | `$\beta$`  | γ      | `$\gamma$` |
| δ      | `$\delta$` | ε      | `$\epsilon$`|
| π      | `$\pi$`    | $\vec{a}$ | `$\vec{a}$` |
| $\hat{a}$ | `$\hat{a}$` | $\overrightarrow{AB}$ | `$\overrightarrow{AB}$` |
| $\cdot$ | `$\cdot$` | $\nabla$ | `$\nabla$` |
| $x^2$  | `$x^2$`    | $x_i$  | `$x_i$`    |
| $x^{y+z}$ | `$x^{y+z}$` | $x_{i,j}$ | `$x_{i,j}$` |

## Tables
```tex
\begin{table}
    \centering
    \begin{tabular}{|c|c|}
        \hline
        Cell 1 & Cell 2 \\
        \hline
        Cell 3 & Cell 4 \\
        \hline
    \end{tabular}
    \caption{Table caption}
    \label{tab:mytable}
```

## Figures
```tex
\begin{figure}
    \centering
    \includegraphics[width=0.8\textwidth]{image.png}
    \caption{Figure caption}
    \label{fig:myfigure}
\end{figure}
```

## References
- Cite: `\cite{key}`
- Label: `\label{sec:section}`
- Reference: `\ref{sec:section}`

## Bibliography
```tex
\bibliographystyle{plain}
\bibliography{references}
```
