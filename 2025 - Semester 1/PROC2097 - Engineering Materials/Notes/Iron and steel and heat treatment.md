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

curie point

```tikz
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
        ytick={0,500,1000,1500},
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
        
        % Labels
        \node[above] at (axis cs:0.8,1493) {Eutectic Point};
        \node[above] at (axis cs:2.1,1410) {Eutectoid Point};
        \node[below] at (axis cs:4.3,1000) {Cementite};
        \node[right] at (axis cs:6.7,727) {Fe$_3$C};
    \end{axis}
\end{tikzpicture}

\end{document}
```