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
\begin{tikzpicture}[scale=0.8]

% Coordinate system
\draw[->, thick] (0,0) -- (8,0) node[right] {Carbon Content (wt.\%)};
\draw[->, thick] (0,0) -- (0,7) node[above] {Temperature (C)};

% Grid marks
\foreach \x in {0,2,4,6}
    \draw (\x,0) -- (\x,-0.1) node[below] {\x};
\foreach \y in {0,2,4,6}
    \draw (0,\y) -- (-0.1,\y) node[left] {\pgfmathparse{int(\y*200)}\pgfmathresult};

% Phase boundaries
\draw[thick] (0,6) -- (6,3); % Liquidus
\draw[thick] (0,5) -- (6,3); % Solidus
\draw[thick] (0,3.5) -- (6,3.5); % Eutectoid line
\draw[thick] (2,6) to[out=-80,in=150] (4.3,4.5) to[out=-30,in=180] (6,3.8);

% Phase regions
% Liquid (yellow)
\fill[yellow!20] (0,6) -- (6,3) -- (6,6) -- cycle;
% Austenite (blue)
\fill[blue!20] (0,5) -- (6,3) -- (6,3.5) -| (0,3.5) -- cycle;
% Ferrite (green)
\fill[green!20] (0,0) rectangle (2.3,3.5);
% Cementite (red)
\fill[red!20] (2.3,3.5) rectangle (6,0);

% Labels
\node at (3,5.5) {Liquid};
\node[blue] at (3,4.5) {Austenite (γ)};
\node[green] at (1,1.5) {Ferrite (α)};
\node[red] at (4.5,1.5) {Cementite (Fe$_3$C)};
\node at (3,3.2) {Pearlite (α+Fe$_3$C)};

% Critical points
\fill (4.3,4.5) circle (2pt) node[above right] {Eutectic (4.3\%, 1147C)};
\fill (2.3,3.5) circle (2pt) node[below right] {Eutectoid (0.76\%, 727C)};

% Dashed composition lines
\draw[dashed] (2.3,0) -- (2.3,3.5);
\draw[dashed] (4.3,0) -- (4.3,4.5);

% Boundary labels
\node[rotate=-20] at (3.5,4.2) {Liquidus};
\node[rotate=-20] at (3,3.8) {Solidus};
\node at (5,3.5) {Eutectoid Line};

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

