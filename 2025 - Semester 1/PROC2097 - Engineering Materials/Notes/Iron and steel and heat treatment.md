### Types of Steel:
#metallurgy
- Stainless Steel aka. corrosion-resistant steel **CRES**
- Mild Steel aka. Low Carbon Steel (between 0.05-0.25% carbon content)
- Alloyed Steel (usually alloyed with nickel and chromium)
- Tool Steel (abrasion resistant steel)

### Types of Iron:
#metallurgy
- Cast Iron (higher than 2% carbon content and silicon content between 1–3%)
- Pig iron (between 2-4.5% carbon content)
- Steel (between 0.25-2% carbon content)
- Wrought Iron (less than 0.25% carbon content)

### Phases of Metal:
#metallurgy

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
#metallurgy

```tikz
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}
    % Axes
    \draw[thick,->] (0,1) -- (7,1) node[right] {Time};
    \draw[thick,->] (0,1) -- (0,6) node[above] {Temperature ($^\circ$C)};
    
    % Critical temperatures
    \draw[dashed] (0,5) -- (6.5,5) node[right] {A3 (Austenite Formation)};
    \draw[dashed] (0,3) -- (6.5,3) node[right] {A1 (Eutectoid Temperature)};

    % Full Annealing Curve
    \draw[thick,red] (1,1) .. controls (1.5,5.5) and (3,5.5) .. (4,5)
                        .. controls (4.5,4.5) and (5,3) .. (6,1);
    \node[right, red] at (6,5.5) {Full Annealing};

    % Partial Annealing Curve
    \draw[thick,blue] (1.5,1) .. controls (2,3.8) and (3,3.8) .. (4,3.5)
                        .. controls (4.5,3.2) and (5,2.5) .. (5.5,1);
    \node[right, blue] at (5.5,3.8) {Partial Annealing};

    % Subcritical Annealing Curve
    \draw[thick,green] (2,1) .. controls (2.5,2.5) and (3,2.5) .. (3.5,2.2)
                        .. controls (4,2) and (4.5,1.8) .. (5,1);
    \node[right, green] at (5,2.5) {Subcritical Annealing};

\end{tikzpicture}

\end{document}

```

### Magnetisation:
#metallurgy
```tikz
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}
    % Axes
    \draw[thick,->] (0,0) -- (7,0) node[right] {Temperature ($^\circ$C)};
    \draw[thick,->] (0,0) -- (0,6) node[above] {Magnetization (M)};
    
    % Curie Temperature (Tc)
    \draw[dashed] (4,0) -- (4,5) node[right] {Curie Point $T_C$};
    
    % Magnetization Curve
    \draw[thick,blue] (1,5) .. controls (3,4.5) and (3.8,3) .. (4,2) 
                        .. controls (4.2,1) and (4.8,0.5) .. (6,0.2);
    
    % Phase Labels
    \node[left, blue] at (1,5) {Ferromagnetic};
    \node[right, blue] at (6,0.5) {Paramagnetic};

\end{tikzpicture}

\end{document}

```

```tikz
\begin{document}
% In this diagram:
% - The horizontal axis is the carbon content in wt% (scaled so that 1 wt% = 25 units).
%   (Thus 0.76 wt% is at x = 0.76*25 = 19, 4.3 wt% is at x = 107.5, and 6.67 wt% is about x = 167.)
% - The vertical axis is temperature in °C.
% - Key critical points (Eutectoid and Eutectic) are marked.
\begin{tikzpicture}[scale=0.05]
    % Draw axes
    \draw[->, thick] (0,0) -- (170,0) node[right] {Carbon Content (wt\%)};
    \draw[->, thick] (0,0) -- (0,1600) node[above] {Temperature (C)};
    
    % X-axis ticks and labels (using our scaling: 1 wt% = 25 units)
    \draw (0,0) -- (0,-20) node[below] {0};
    \draw (19,0) -- (19,-20) node[below] {0.76};
    \draw (107.5,0) -- (107.5,-20) node[below] {4.3};
    \draw (167,0) -- (167,-20) node[below] {6.67};
    
    % Y-axis ticks and labels (temperatures in °C)
    \draw (0,727) -- (-10,727) node[left] {727};
    \draw (0,1147) -- (-10,1147) node[left] {1147};
    \draw (0,1538) -- (-10,1538) node[left] {1538};
    
    % Draw dashed lines for key boundaries
    % Vertical lines at the eutectoid and eutectic compositions:
    \draw[dashed] (19,0) -- (19,1600);
    \draw[dashed] (107.5,0) -- (107.5,1600);
    % Horizontal lines at key temperatures:
    \draw[dashed] (0,727) -- (167,727);
    \draw[dashed] (0,1147) -- (167,1147);
    \draw[dashed] (0,1538) -- (167,1538);
    
    % Fill phase regions with colors
    % 1. Ferrite (α): low carbon (<0.76 wt%) and low temperature (below 727°C)
    \fill[red!30] (0,0) rectangle (19,727);
    \node at (9.5,360) {Ferrite ($\alpha$)};
    
    % 2. Austenite (γ): roughly between 0 wt% and 4.3 wt% C, above 727°C.
    % Here we approximate its region as the triangle joining (0,727), (0,1538) and (107.5,1147)
    \fill[blue!30] (0,727) -- (0,1538) -- (107.5,1147) -- cycle;
    \node at (35,1200) {Austenite ($\gamma$)};
    
    % 3. Cementite (Fe$_3$C): high-carbon region (4.3–6.67 wt% C) at lower temperatures (below 1147°C)
    \fill[orange!30] (107.5,0) rectangle (167,1147);
    \node at (137,570) {Cementite (Fe$_3$C)};
    
    % 4. Liquid: region above the liquidus. We approximate the liquid area as the polygon
    % bounded by (0,1538), (107.5,1147), (167,1200), (167,1600) and (0,1600)
    \fill[yellow!30] (0,1538) -- (107.5,1147) -- (167,1200) -- (167,1600) -- (0,1600) -- cycle;
    \node at (100,1550) {Liquid};
    
    % Mark key transformation points
    % Eutectoid point (where austenite transforms to ferrite + cementite)
    \filldraw (19,727) circle (4);
    \node[above right] at (19,727) {Eutectoid (0.76\%, 727C)};
    
    % Eutectic point (where liquid transforms to austenite + cementite in cast iron)
    \filldraw (107.5,1147) circle (4);
    \node[above right] at (107.5,1147) {Eutectic (4.3\%, 1147C)};
\end{tikzpicture}
\end{document}

```

```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[scale=1.2]

  % Axes
  \draw[->, thick] (0,0) -- (8,0) node[right] {Wt\% C};
  \draw[->, thick] (0,0) -- (0,7) node[above] {Temperature ($^\circ$C)};

  % Temperature Lines
  \foreach \y/\label in {1.5/727, 3.5/1147, 5.5/1495, 6/1538}
    \draw[dashed, gray] (0,\y) -- (8,\y) node[left] {\label};

  % Composition Labels
  \foreach \x/\label in {0/0, 2/0.76, 4.3/4.3, 6.67/6.67}
    \node[below] at (\x,0) {\label};

  % Regions and Labels (Simplified)
  \fill[green!20, opacity=0.5] (0,0) -- (2,1.5) -- (0,3.5) -- cycle;
  \node at (1,1) {$\alpha$};

  \fill[blue!20, opacity=0.5] (2,1.5) -- (4.3,3.5) -- (4.3,5.5) -- (2,3.5) -- cycle;
  \node at (3,3) {$\gamma$};

  \fill[yellow!20, opacity=0.5] (4.3,1.5) -- (6.67,5.5) -- (6.67,0) -- cycle;
  \node at (5.5,2) {Fe$_3$C};

  \fill[purple!20, opacity=0.5] (2,1.4) rectangle (2.1,1.6);
  \node at (2,1) {Pearlite};

  \fill[orange!20, opacity=0.5] (4.25,3.4) rectangle (4.35,3.6);
  \node at (4.3,3) {Ledeburite};

  \fill[red!20, opacity=0.5] (4.3,5.5) -- (8,6) -- (8,5.5) -- cycle;
  \node at (6,5.8) {Liquid};

  \fill[cyan!20, opacity=0.5] (0,5.5) -- (0.5,6) -- (0.3,5.5) -- cycle;
  \node at (0.2,5.8) {$\delta$};

  % Two-Phase Regions (Simplified)
    %L+gamma
  \fill[blue!10, opacity=0.5] (4.3,5.5) -- (2,3.5) -- (4.3,3.5) -- (4.3,6);
  \node at (3.5,4.5) {L + $\gamma$};
    %L+Fe3C
  \fill[yellow!10, opacity=0.5] (4.3,5.5) -- (6.67,5.5) -- (6.67,6) -- (4.3,6);
  \node at (5.5,5.8) {L + Fe$_3$C};
    %gamma+Fe3C
  \fill[blue!10, opacity=0.5] (4.3,1.5) -- (4.3,3.5) -- (6.67,5.5) -- (4.3,5.5);
  \node at (5.2,3) {$\gamma$ + Fe$_3$C};
    %alpha+Fe3C
  \fill[green!10, opacity=0.5] (2,1.5) -- (4.3,1.5) -- (4.3,3.5) -- (2,1.5);
  \node at (3,2) {$\alpha$ + Fe$_3$C};

  % Lines between regions (Simplified)
  \draw (2,1.5) -- (4.3,3.5) -- (4.3,5.5) -- (6.67,5.5);
  \draw (0,3.5) -- (2,1.5);
  \draw (0,5.5) -- (0.5,6);

  % Title
  \node at (4,7) {Fe-C Phase Diagram};

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

