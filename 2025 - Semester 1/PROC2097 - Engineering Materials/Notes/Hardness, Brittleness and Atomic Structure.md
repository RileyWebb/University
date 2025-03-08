# Atomic Structure

## Crystalline Structures
#metallurgy
A **crystalline atomic structure** is an ordered arrangement of atoms that follows a repeating pattern over long distances. This structure forms a **crystal lattice**, where atoms, ions, or molecules are arranged in a highly organized and predictable way. The repeating unit in this structure is called a **unit cell**, which defines the basic building block of the crystal.

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

**Types of Crystalline Structures:**

| Structure                    | Packing Efficiency | Ductility  | Density | Examples                                  |
| ---------------------------- | ------------------ | ---------- | ------- | ----------------------------------------- |
| BCC (Body-Centered Cubic)    | 68%                | Low        | Medium  | Iron (Ferrite), Tungsten, Chromium        |
| FCC (Face-Centered Cubic)    | 74%                | High       | High    | Aluminum, Copper, Gold, Silver, Austenite |
| HCP (Hexagonal Close-Packed) | 74%                | Medium-Low | High    | Magnesium, Titanium, Zinc, Cobalt         |
**Examples:**

- **Metals:** Most metals like iron, aluminium, and copper are crystalline.
- **Minerals and Gemstones:** Quartz (SiO₂), diamonds, and salt (NaCl) all exhibit strong crystalline structures.
- **Semiconductors:** Silicon and germanium, used in electronics, have highly ordered crystalline structures.
- **Ionic Crystals:** Materials like sodium chloride (table salt) form crystalline lattices due to electrostatic attraction between ions.

## Amorphous Structures
#metallurgy
An **amorphous atomic structure** is a disordered arrangement of atoms that lacks long-range periodic order, distinguishing it from crystalline structures. Instead of forming a repeating lattice, atoms in an amorphous material are arranged in an irregular and non-uniform manner, similar to how atoms in a liquid are arranged but with more rigidity.

**Visualisation:**
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1, every node/.style={circle,draw,fill=black,inner sep=0pt}]
  % Define atoms: format is index/x-coordinate/y-coordinate/size
  \foreach \n/\x/\y/\s in {
    0/0.2/0.2/0.15,
    1/0.5/0.3/0.25,
    2/0.9/0.4/0.15,
    3/1.3/0.2/0.25,
    4/1.6/0.6/0.15,
    5/2.0/0.5/0.25,
    6/2.3/0.9/0.15,
    7/2.6/0.7/0.25,
    8/2.9/1.1/0.15,
    9/3.2/0.8/0.25,
    10/0.4/1.0/0.15,
    11/0.7/1.3/0.25,
    12/1.0/1.6/0.15,
    13/1.4/1.4/0.25,
    14/1.8/1.8/0.15,
    15/2.1/1.5/0.25,
    16/2.5/1.9/0.15,
    17/2.8/1.6/0.25,
    18/3.1/2.0/0.15,
    19/3.4/1.7/0.25,
    20/1/0.7/0.15,
    21/1.2/1/0.25,
    22/1.8/1.1/0.25
  }
  {
    \node[minimum size=\s cm] (A\n) at (\x,\y) {};%{A\n};
  }
  
  % Group 1 connections (points 0 to 9)
  \draw (A0) -- (A1);
  \draw (A1) -- (A2);
  \draw (A2) -- (A3);
  \draw (A3) -- (A4);
  \draw (A4) -- (A5);
  \draw (A5) -- (A6);
  \draw (A6) -- (A7);
  \draw (A7) -- (A8);
  \draw (A8) -- (A9);
  
  % Group 2 connections (points 10 to 19)
  \draw (A10) -- (A11);
  \draw (A11) -- (A12);
  \draw (A12) -- (A13);
  \draw (A13) -- (A14);
  \draw (A14) -- (A15);
  \draw (A15) -- (A16);
  \draw (A16) -- (A17);
  \draw (A17) -- (A18);
  \draw (A18) -- (A19);
  
  % Cross connections between groups
  \draw (A0) -- (A10);
  \draw (A1) -- (A10);
  \draw (A11) -- (A21);
  \draw (A13) -- (A21);
  %\draw (A20) -- (A10);
  \draw (A21) -- (A10);
  \draw (A20) -- (A21);
  \draw (A20) -- (A2);
  \draw (A22) -- (A13);
  \draw (A22) -- (A15);
  \draw (A22) -- (A4);
  \draw (A22) -- (A6);
  \draw (A8) -- (A15);
  \draw (A8) -- (A17);
  \draw (A8) -- (A19);
  %\draw (A4) -- (A11);
  %\draw (A6) -- (A12);
  %\draw (A8) -- (A13);
  %\draw (A9) -- (A14);
  %\draw (A5) -- (A15);
  %\draw (A7) -- (A16);
  %\draw (A3) -- (A17);
  %\draw (A1) -- (A18);
  %\draw (A0) -- (A19);
  
  % Extra cross connections for added irregularity
  %\draw (A12) -- (A15);
  %\draw (A13) -- (A16);
\end{tikzpicture}
\end{document}

```
**Examples:**

- **Glass** (SiO₂-based) – A classic example of an amorphous solid.
- **Amorphous Silicon** – Used in thin-film solar cells and displays.
- **Metallic Glasses** – Amorphous metals that have superior strength and corrosion resistance.
- **Polymers** – Many plastics, like amorphous polyethylene terephthalate (PET), have disordered structures.

## Polycrystalline Structures
#metallurgy
A **polycrystalline structure** is composed of many small crystalline regions, called **grains**, which are randomly oriented relative to one another. Each grain has a well-defined **crystalline structure**, but the overall material lacks a single uniform crystal lattice due to the presence of **grain boundaries**, which separate different grains.

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

**Examples:**

- **Metals and Alloys** – Most engineering metals (steel, aluminum, copper) are polycrystalline.
- **Ceramics** – Polycrystalline ceramics (such as alumina and silicon carbide) are used for high-strength applications.
- **Semiconductors** – Polycrystalline silicon (polysilicon) is used in solar cells and thin-film transistors.
- **Ice and Rocks** – Many naturally occurring geological materials (e.g., granite) are polycrystalline.

## Brinell Hardness Number:

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
