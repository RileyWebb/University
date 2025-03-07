### Brinell Hardness Number:

```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[scale=1.5]

  % Indenter (Ball)
  \draw[fill=gray!50] (0,0) circle (1);
  \draw (0,0) circle (1);

  % Material Surface
  \draw (-2,-1.5) -- (2,-1.5) -- (2,-2.5) -- (-2,-2.5) -- cycle;

  % Indentation
  \begin{scope}
    \clip (0,-2) circle (1);
    \clip (-2,-1.5) rectangle (2,-2.5);
    %\draw[fill=white] (0,0) circle (1);
  \end{scope}

  % Diameter of Indenter (D)
  \draw[<->, white, thick] (-1,0) -- (1,0);
  \node[above, white] at (0,0) {$D$};

  % Diameter of Indentation (d)
  \draw[<->] (-0.8,-2) -- (0.8,-2);
  \node[below] at (0,-2) {$d$};

  % Force (F)
  \draw[->, thick] (0,1.5) -- (0,1);
  \node[above] at (0,1.5) {$F$};

  % Brinell Hardness Number (BHN) Formula
  \node[below] at (0,-3) {
    $\text{BHN} = \frac{2P}{\pi D (D - \sqrt{D^2 - d^2})}$
  };

  % Annotations
  \node[left] at (-1.5,0) {Indenter (Ball)};
  \node[right] at (1.5,-2) {Indentation};
  %\node[left] at (-1.5,-2) {Material};

\end{tikzpicture}
\end{document}
```

where;
$P$ is the force in Kilograms,
$D$ is the diameter of the sphere in Millimetres,
and $d$ is the diameter of the indent in Millimetres.

# Atomic Structure
| Structure                    | Packing Efficiency | Ductility  | Density | Examples                                  |
| ---------------------------- | ------------------ | ---------- | ------- | ----------------------------------------- |
| BCC (Body-Centered Cubic)    | 68%                | Low        | Medium  | Iron (Ferrite), Tungsten, Chromium        |
| FCC (Face-Centered Cubic)    | 74%                | High       | High    | Aluminum, Copper, Gold, Silver, Austenite |
| HCP (Hexagonal Close-Packed) | 74%                | Medium-Low | High    | Magnesium, Titanium, Zinc, Cobalt         |
