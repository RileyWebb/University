# Atomic Structures
---
## Crystalline Structures
#metallurgy #AI
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
#metallurgy #AI
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
#metallurgy #AI
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

- **Metals and Alloys** – Most engineering metals (steel, aluminium, copper) are polycrystalline.
- **Ceramics** – Polycrystalline ceramics (such as alumina and silicon carbide) are used for high-strength applications.
- **Semiconductors** – Polycrystalline silicon (polysilicon) is used in solar cells and thin-film transistors.
- **Ice and Rocks** – Many naturally occurring geological materials (e.g., granite) are polycrystalline.

## Lattice Structures

> [!NOTE] 
> This data is directly referenced from [Wikipedia](https://en.wikipedia.org/wiki/Crystal_structure#Lattice_systems)

| Lattice system                                                                                                | Point group  <br> | Primitive (P)                                                                                                                                                                                                                 | Base-cantered (S)                                                                                                                                                                                                                                                             | Body-centered (I)                                                                                                                                                                                                                                                             | Face-centered (F)                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Triclinic](https://en.wikipedia.org/wiki/Triclinic "Triclinic") (a)                                          | $C_{i}$           | [![Triclinic](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Triclinic.svg/80px-Triclinic.svg.png)](https://en.wikipedia.org/wiki/File:Triclinic.svg "Triclinic")<br>aP                                            |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |
| [Monoclinic](https://en.wikipedia.org/wiki/Monoclinic "Monoclinic") (m)                                       | $C_{2h}$          | [![Monoclinic, simple](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/Monoclinic.svg/80px-Monoclinic.svg.png)](https://en.wikipedia.org/wiki/File:Monoclinic.svg "Monoclinic, simple")<br><br>mP                   | [![Monoclinic, centered](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Base-centered_monoclinic.svg/80px-Base-centered_monoclinic.svg.png)](https://en.wikipedia.org/wiki/File:Base-centered_monoclinic.svg "Monoclinic, centered")<br><br>mS                     |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |
| [Orthorhombic](https://en.wikipedia.org/wiki/Orthorhombic "Orthorhombic") (o)                                 | $D_{2h}$          | [![Orthorhombic, simple](https://upload.wikimedia.org/wikipedia/commons/thumb/d/dd/Orthorhombic.svg/80px-Orthorhombic.svg.png)](https://en.wikipedia.org/wiki/File:Orthorhombic.svg "Orthorhombic, simple")<br><br>oP         | [![Orthorhombic, base-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b4/Base-centered_orthorhombic.svg/80px-Base-centered_orthorhombic.svg.png)](https://en.wikipedia.org/wiki/File:Base-centered_orthorhombic.svg "Orthorhombic, base-centered")<br><br>oS | [![Orthorhombic, body-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Body-centered_orthorhombic.svg/80px-Body-centered_orthorhombic.svg.png)](https://en.wikipedia.org/wiki/File:Body-centered_orthorhombic.svg "Orthorhombic, body-centered")<br><br>oI | [![Orthorhombic, face-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/Face-centered_orthorhombic.svg/80px-Face-centered_orthorhombic.svg.png)](https://en.wikipedia.org/wiki/File:Face-centered_orthorhombic.svg "Orthorhombic, face-centered")<br><br>oF |
| [Tetragonal](https://en.wikipedia.org/wiki/Tetragonal "Tetragonal") (t)                                       | $D_{4h}$          | [![Tetragonal, simple](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Tetragonal.svg/80px-Tetragonal.svg.png)](https://en.wikipedia.org/wiki/File:Tetragonal.svg "Tetragonal, simple")<br><br>tP                   |                                                                                                                                                                                                                                                                               | [![Tetragonal, body-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Body-centered_tetragonal.svg/80px-Body-centered_tetragonal.svg.png)](https://en.wikipedia.org/wiki/File:Body-centered_tetragonal.svg "Tetragonal, body-centered")<br><br>tI           |                                                                                                                                                                                                                                                                               |
| [Hexagonal](https://en.wikipedia.org/wiki/Hexagonal_crystal_family "Hexagonal crystal family") (Rhombohedral) | $D_{3d}$          | [![Rhombohedral](https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Rhombohedral.svg/80px-Rhombohedral.svg.png)](https://en.wikipedia.org/wiki/File:Rhombohedral.svg "Rhombohedral")<br><br>hR                         |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |
| Hexagonal                                                                                                     | $D_{6h}$          | [![Hexagonal](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Hexagonal_latticeFRONT.svg/80px-Hexagonal_latticeFRONT.svg.png)](https://en.wikipedia.org/wiki/File:Hexagonal_latticeFRONT.svg "Hexagonal")<br><br>hP |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                               |
| [Cubic](https://en.wikipedia.org/wiki/Cubic_crystal_system "Cubic crystal system") (c)                        | $O_{h}$           | [![Cubic, simple](https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Cubic.svg/80px-Cubic.svg.png)](https://en.wikipedia.org/wiki/File:Cubic.svg "Cubic, simple")<br><br>cP                                            |                                                                                                                                                                                                                                                                               | [![Cubic, body-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Cubic-body-centered.svg/80px-Cubic-body-centered.svg.png)](https://en.wikipedia.org/wiki/File:Cubic-body-centered.svg "Cubic, body-centered")<br><br>cI                                    | [![Cubic, face-centered](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Cubic-face-centered.svg/80px-Cubic-face-centered.svg.png)](https://en.wikipedia.org/wiki/File:Cubic-face-centered.svg "Cubic, face-centered")<br><br>cF                                    |
## Calculating Atomic Packing Factors and Density
$$\rho=\dfrac{nA}{V_{c}N_{A}}$$
where;
$n$ is the number of atoms,
$A$ is the atomic mass,
$V_{c}$ is the volume of a unit cell,
$N_{A}$ is Avogadro’s number ($N_{A}=6.022 \cdot 10^{23}$)
and $\rho$ is the density.

# Atomic Bonding
---
#AI
### Nonpolar Covalent Bonding

- **Description**: Electrons are shared equally between atoms with **similar electronegativity**.
- **Example**: $O_2$ (oxygen gas), $N_2$ (nitrogen gas), $CH_4$ (methane).
- **Strength**: Strong.
- **Properties**: No partial charges, usually insoluble in water, low reactivity.

### Polar Covalent Bonding

- **Description**: Electrons are **unequally shared**, causing partial charges (δ+ and δ−) due to a **difference in electronegativity**.
- **Example**: $H_2O$ (water), $NH_3$ (ammonia), $HF$ (hydrofluoric acid).
- **Strength**: Strong.
- **Properties**: Partial positive/negative charges, higher solubility in water, can form hydrogen bonds.

### Ionic Bonding

- **Description**: Complete transfer of electrons creates oppositely charged ions.
- **Example**: $NaCl$ (table salt), $MgO$ (magnesium oxide).
- **Strength**: Strong.
- **Properties**: High melting/boiling points, conductive in molten/dissolved states.

### Metallic Bonding

- **Description**: Positive metal ions are surrounded by a **sea of delocalized electrons**.
- **Example**: $Cu$ (copper), $Fe$ (iron), $Al$ (aluminium).
- **Strength**: Strong.
- **Properties**: High electrical and thermal conductivity, malleable and ductile.

### Hydrogen Bonding (Intermolecular Bonding)

- **Description**: A weak attraction between a hydrogen atom (bonded to $N$, $O$, or $F$) and another electronegative atom.
- **Example**: $H_2O$ (water), DNA base pairing.
- **Strength**: Weaker than covalent/ionic bonds but stronger than Van der Waals forces.
- **Properties**: Raises boiling/melting points, important in biological molecules.

### Van der Waals Forces (Intermolecular Forces)

- **Description**: Weak, temporary attractions between molecules due to fluctuating electron distributions.
- **Example**: Noble gases (like $Ar$, $Ne$), nonpolar molecules (like $CH_{4}$).
- **Strength**: Weakest.
- **Properties**: Low boiling/melting points, significant in gases and molecular crystals.