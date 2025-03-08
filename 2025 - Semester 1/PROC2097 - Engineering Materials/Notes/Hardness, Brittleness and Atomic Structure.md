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
## Crystalline Structures

**Visualisation:**

```tikz
\usepackage{tikz}
\usepackage{chemfig}
\usepackage{pgfplots}
\usepackage{amsfonts}

\begin{document}
\begin{tikzpicture}

  % Graph 1: Crystalline (Ordered)
  %\begin{scope}[shift={(0,0)}]

  %\node[anchor=south] at (1.5,-0.7) {Crystalline (Ordered)};

  \foreach \x in {0,0.5,...,3}
    \foreach \y in {0,0.5,...,2}
      \fill (\x,\y) circle (2pt);

  \foreach \x in {0,0.5,...,2.5}
    \foreach \y in {0,0.5,...,2}
      \draw (\x,\y) -- (\x+0.5,\y);

  \foreach \x in {0,0.5,...,3}
    \foreach \y in {0,0.5,...,1.5}
      \draw (\x,\y) -- (\x,\y+0.5);
  %\end{scope}

\end{tikzpicture}
\end{document}
```


## Amorphous Structures

**Visualisation:**
```tikz
\usepackage{tikz}
\usetikzlibrary{math}
\begin{document}

\begin{tikzpicture}
 

  \foreach \x in {1,...,8}
    \foreach \y in {1,...,5}
	    \coordinate (A\x\y) at (\x+rand/4, \y+rand/4);

  \foreach \x in {1,...,8}
    \foreach \y in {1,...,5}
      \fill (A\x\y) circle (2pt) node[above] {A\x\y};


  \foreach \x in {2,...,7}
  {
	
    \foreach \y in {2,...,4}
    {

        
	  %\draw (A\x\y) -- (\coordname);
	  %\tikzmath{\xm = \x-1; \xp =\x+1; \ym = \y-1; \yp =\y+1; }
	  %\pgfmathsetmacro{\xm}{-1+\x}
	  %\pgfmathsetmacro{\xp}{1+\x}
	  %\pgfmathsetmacro{\ym}{-1+\y}
	  %\pgfmathsetmacro{\yp}{1+\y}
	  
	  %\foreach \j in {\xm,...,\xp}
	  %  \foreach \k in {\ym,...,\yp}
	  %    \draw (A\x\y) -- (A\j\k);
	};
};

\end{tikzpicture}

\end{document}

```

## Polycrystalline Structures

**Visualisation:**

```tikz
\usepackage{tikz}
\usetikzlibrary{shapes.geometric, calc}

\begin{document}

\begin{tikzpicture}

    % Define colors for different grains
    \definecolor{grain1}{RGB}{255,200,200}
    \definecolor{grain2}{RGB}{200,255,200}
    \definecolor{grain3}{RGB}{200,200,255}
    \definecolor{grain4}{RGB}{255,255,200}
    
    % Draw irregular grains
    \fill[grain1] (0,0) -- (2,1) -- (2.5,3) -- (1.5,4) -- (0,3) -- cycle;
    \fill[grain2] (2,1) -- (4,0) -- (5,2) -- (3,3) -- (2.5,3) -- cycle;
    \fill[grain3] (1.5,4) -- (2.5,3) -- (3,3) -- (4,4.5) -- (2,5) -- cycle;
    \fill[grain4] (5,2) -- (6,3) -- (6,5) -- (4,4.5) -- (3,3) -- cycle;

    % Outline grain boundaries with thick black lines
    \draw[thick] (0,0) -- (2,1) -- (2.5,3) -- (1.5,4) -- (0,3) -- cycle;
    \draw[thick] (2,1) -- (4,0) -- (5,2) -- (3,3) -- (2.5,3) -- cycle;
    \draw[thick] (1.5,4) -- (2.5,3) -- (3,3) -- (4,4.5) -- (2,5) -- cycle;
    \draw[thick] (5,2) -- (6,3) -- (6,5) -- (4,4.5) -- (3,3) -- cycle;

    % Label grains
    \node[white] at (1,2) {\textbf{Grain A}};
    \node[white] at (3,1.5) {\textbf{Grain B}};
    \node[white] at (2.5,4) {\textbf{Grain C}};
    \node[white] at (5,3.5) {\textbf{Grain D}};

    % Label grain boundaries
    %\draw[->] (2.75,2.5) -- (3.5,1.5) node[midway, above, sloped, black] {Grain Boundary};

\end{tikzpicture}

\end{document}

```
