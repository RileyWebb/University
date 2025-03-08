
```tikz
\usepackage{chemfig}

\begin{document}

% Example of a polymer chain (polyethylene)
\chemfig{
    \chemleft[
    \chemfig{
        -[::30]CH_2-[:30]CH(-[::-60]CH_2-[::30]*5(
            -[::30]CH_2-[::-60]CH_2-
        ))
        -[::-60]CH_2-
    }
    \chemright]_{n}
}

\end{document}

```
