
```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]
    % Straight carbon backbone
    \draw (0,0) coordinate (C0) -- ++(1,0) coordinate (C1) -- ++(1,0) coordinate (C2) -- ++(1,0) coordinate (C3) -- ++(1,0) coordinate (C4);

    % Hydrogens (vertical arrangement)
    \foreach \pos in {C0,C1,C2,C3,C4} {
        \draw (\pos) -- ++(0,0.5) node[above] {\footnotesize H};
        \draw (\pos) -- ++(0,-0.5) node[below] {\footnotesize H};
    }

    % Carbon labels
    \foreach \pos in {C0,C1,C2,C3,C4} {
        \node[circle, fill=white, inner sep=1pt] at (\pos) {\footnotesize C};
    }

    \draw (-1.1,0) coordinate (O1) -- ++(0.95,0);
	\draw (5.1,0) coordinate (O2) -- ++(-0.95,0);

	        \node[circle, fill=white, inner sep=1pt] at (O1) {\footnotesize O};
	        \node[circle, fill=white, inner sep=1pt] at (O2) {\footnotesize O};

\end{tikzpicture}
\end{document}
```
