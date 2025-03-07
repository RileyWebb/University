**Types of Steel:**
- Stainless Steel aka. corrosion-resistant steel **CRES**
- Mild Steel aka. Low Carbon Steel (between 0.05-0.25% carbon content)
- Alloyed Steel (usually alloyed with nickel and chromium)
- Tool Steel (abrasion resistant steel)

**Types of Iron:**
- Cast Iron (higher than 2% carbon content and silicon content between 1–3%)
- Pig iron (between 2-4.5% carbon content)
- Steel (between 0.25-2% carbon content)
- Wrought Iron (less than 0.25% carbon content)

**Annealing:**

```tikz
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={Time (s)},
        ylabel={Temperature (°C)},
        xmin=0, xmax=12,
        ymin=0, ymax=1000,
        xtick={0,2,4,6,8,10,12},
        ytick={0,200,400,600,800,1000},
        grid=major,
        samples=100,
        domain=0:12
    ]
        % Full Annealing
        \addplot[blue, thick] coordinates {
            (0, 25) (2, 900) (4, 900) (6, 500) (8, 300) (10, 25)
        };
        
        % Partial Annealing
        \addplot[red, thick, dashed] coordinates {
            (0, 25) (2, 750) (4, 750) (6, 500) (8, 300) (10, 25)
        };
        
        % Subcritical Annealing
        \addplot[green, thick, dotted] coordinates {
            (0, 25) (2, 600) (4, 600) (6, 500) (8, 300) (10, 25)
        };
        
        % Labels
        \node[above] at (axis cs:2,900) {Full Annealing};
        \node[above] at (axis cs:2,750) {Partial Annealing};
        \node[above] at (axis cs:2,600) {Subcritical Annealing};
    \end{axis}
\end{tikzpicture}

\end{document}
```

curie point

```
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={Carbon Content (\%)},
        ylabel={Temperature (°C)},
        xmin=0, xmax=6.7,
        ymin=0, ymax=1600,
        xtick={0,0.8,2.1,4.3,6.7},
        ytick={0,500,727,1000,1147,1300,1410,1493,1538},
        grid=major,
        samples=100,
        domain=0:6.7
    ]
        % Liquidus line
        \addplot[red, thick] coordinates {(0,1538) (0.8,1493) (2.1,1410) (4.3,1300) (6.7,1147)};
        
        % Solidus line
        \addplot[blue, thick] coordinates {(0,1538) (0.8,1435) (2.1,1130) (4.3,1000) (6.7,727)};
        
        % Eutectoid horizontal line
        \addplot[dashed, black, thick] coordinates {(0,727) (6.7,727)};
        
        % Eutectic horizontal line
        \addplot[dashed, black, thick] coordinates {(0,1147) (6.7,1147)};
        
        % Phase labels
        \node[above] at (axis cs:0.8,1493) {Eutectic Point};
        \node[above] at (axis cs:2.1,1410) {Eutectoid Point};
        \node[below] at (axis cs:4.3,1000) {Cementite};
        \node[right] at (axis cs:6.7,727) {Fe$_3$C};
        \node[left] at (axis cs:0.2,1200) {Austenite};
        \node[left] at (axis cs:0.2,600) {Ferrite + Cementite};
        \node[left] at (axis cs:3,1200) {Liquid + Austenite};
        \node[left] at (axis cs:3,900) {Pearlite + Cementite};
    \end{axis}
\end{tikzpicture}

\end{document}
```



```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[scale=1.2]

  % Axes
  \draw[->, thick] (0,0) -- (8,0) node[right] {Composition (e.g., % Carbon)};
  \draw[->, thick] (0,0) -- (0,6) node[above] {Temperature};

  % Eutectic Point
  \draw[fill=red] (4,2) circle (0.1) node[above right] {Eutectic Point};

  % Austenite Region
  \draw[fill=blue!20, opacity=0.5] (1,3) -- (6,5) -- (6,3) -- (1,1) -- cycle;
  \node at (3.5,4) {Austenite ($\gamma$)};

  % Ferrite Region
  \draw[fill=green!20, opacity=0.5] (0,0) -- (1,1) -- (1,3) -- (0,2) -- cycle;
  \node at (0.5,1.5) {Ferrite ($\alpha$)};

  % Cementite Region
  \draw[fill=yellow!20, opacity=0.5] (6,0) -- (7,1) -- (7,3) -- (6,3) -- cycle;
  \node at (6.5,2) {Cementite (Fe$_3$C)};

  % Pearlite Region (Simplified, usually within Eutectoid)
  \draw[fill=purple!20, opacity=0.5] (3.8,1.8) rectangle (4.2,2.2);
  \node at (4,1.5) {Pearlite};

  % Liquid Region
  \draw[fill=orange!20, opacity=0.5] (3,5) -- (5,5.8) -- (8,5.8) -- (8,4) -- (6,3) -- cycle;
  \node at (6,5) {Liquid};

  % Lines separating regions
  \draw (1,1) -- (1,3);
  \draw (6,3) -- (1,3);
  \draw (6,3) -- (7,3);
  \draw (3,5) -- (6,5);
  \draw (5,5.8) -- (6,3);
  \draw (7,1) -- (7,3);

  % Labels for important points
  \node[below] at (0,0) {0};
  \node[below] at (4,0) {Eutectic Composition};
  \node[below] at (7,0) {Max Carbon};

  \node[left] at (0,2) {Temperature 1};
  \node[left] at (0,3) {Temperature 2};
  \node[left] at (0,5) {Temperature 3};

  % Add a title
  \node at (4,6.5) {Simplified Metal Phase Diagram};

\end{tikzpicture}
\end{document}
```

