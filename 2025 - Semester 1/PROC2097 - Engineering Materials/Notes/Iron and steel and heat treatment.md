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

| Phase            | State      | Structure          | Ductility/Hardness              | Example                    |
| ---------------- | ---------- | ------------------ | ------------------------------- | -------------------------- |
| Liquid           | Molten     | No structure       | Flows freely                    | Molten Iron                |
| Alpha (α)        | Solid      | BCC                | Soft, Ductile                   | Ferrite in Steel           |
| Beta (β)         | Solid      | BCC                | Harder than α                   | Brass (Cu-Zn)              |
| Austenite (γ)    | Solid      | FCC                | Ductile, High Carbon Solubility | Steel at High Temperatures |
| Cementite (Fe₃C) | Solid      | Complex            | Very Hard, Brittle              | Iron-Carbon Alloy          |
| Eutectic Point   | Transition | Liquid → 2 Solids  | -                               | Pb-Sn, Iron-Carbon         |
| Eutectoid Point  | Transition | 1 Solid → 2 Solids | -                               | Pearlite in Steel          |

**Annealing:**

```
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

\begin{document}

\begin{tikzpicture}
    % Axes
    \draw[thick,->] (0,0) -- (7,0) node[right] {Composition (\%)};
    \draw[thick,->] (0,0) -- (0,6) node[above] {Temperature ($^\circ$C)};

    % Phase regions
    \draw[thick] (0,5) .. controls (3,4.5) .. (6,5); % Liquidus
    \draw[thick] (0,3) .. controls (2,3.5) .. (6,3); % Solidus
    \draw[thick] (2,3) -- (2,5); % Eutectic Line
    \draw[thick, dashed] (4,1.5) -- (4,5); % Eutectoid Line

    % Labels
    \node at (1,5.5) {Liquid};
    \node at (4,4) {Austenite};
    \node at (5,2.5) {Ferrite + Cementite};
    \node at (2,2.5) {Ferrite};
    \node[below] at (2,0) {Eutectic Point};
    \node[below] at (4,0) {Eutectoid Point};

    % Eutectic and Eutectoid Points
    \filldraw[red] (2,3) circle (2pt);
    \filldraw[blue] (4,1.5) circle (2pt);
    
\end{tikzpicture}

\end{document}

```

