# Stress ($\sigma$)
---
#AI
Stress is a measure of the internal forces acting within a deformable body. It is defined as the force applied per unit area.

**Formula:**
$$\qquad \sigma = \dfrac{F}{A}$$

where;
$\sigma$ is the stress (usually measured in Pascals (Pa)),
$F$ is the force applied (in Newtons (N)),
and $A$ is the cross-sectional area over which the force is applied (in square meters ($m^2$)).

### Types of Stress:

* **Tensile Stress:** Occurs when forces pull on the object, tending to elongate it.
* **Compressive Stress:** Occurs when forces push on the object, tending to shorten it.
* **Shear Stress:** Occurs when forces act parallel to a surface, tending to cause one part of the object to slide over another.
* **Torsional Stress:** A variation of shear stress that occurs when an object is twisted. This twisting action creates a shear stress within the material.
- **Bending Stress:** A combination of tensile, compressive, and shear stresses that occurs when an object is bent. One side of the object experiences tension (stretching), while the opposite side experiences compression.

### Visualisation:

```tikz
\usepackage{tikz}
\usetikzlibrary{decorations.pathmorphing, arrows.meta}

\begin{document}

\begin{tikzpicture}[scale=1.5]

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    % Tensile Stress
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \begin{scope}[xshift=0cm]
        % Original shape (rectangle)
        \draw[thick] (0,0) rectangle (2,1);
        % Arrows for tensile stress
        \draw[->, thick, red] (1,1.2) -- (1,1.5); % Top arrow
        \draw[->, thick, red] (1,-0.2) -- (1,-0.5); % Bottom arrow
        % Deformation effect (stretched rectangle)
        \draw[thick, decorate, decoration={snake, amplitude=2pt, segment length=10pt}] (0.2,1.2) -- (1.8,1.2);
        \draw[thick, decorate, decoration={snake, amplitude=2pt, segment length=10pt}] (0.2,-0.2) -- (1.8,-0.2);
        % Label
        \node[below] at (1,-0.7) {\textbf{Tensile Stress}};
    \end{scope}

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    % Compressive Stress
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \begin{scope}[xshift=4cm]
        % Original shape (rectangle)
        \draw[thick] (0,0) rectangle (2,1);
        % Arrows for compressive stress
        \draw[->, thick, blue] (1,1.5) -- (1,1.2); % Top arrow
        \draw[->, thick, blue] (1,-0.5) -- (1,-0.2); % Bottom arrow
        % Deformation effect (compressed rectangle)
        \draw[thick, decorate, decoration={zigzag, amplitude=2pt, segment length=10pt}] (0.2,1.2) -- (1.8,1.2);
        \draw[thick, decorate, decoration={zigzag, amplitude=2pt, segment length=10pt}] (0.2,-0.2) -- (1.8,-0.2);
        % Label
        \node[below] at (1,-0.7) {\textbf{Compressive Stress}};
    \end{scope}

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    % Shear Stress
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \begin{scope}[xshift=8cm]
        % Original shape (rectangle)
        \draw[thick] (0,0) rectangle (2,1);
        % Arrows for shear stress
        \draw[->, thick, green] (2.2,0.2) -- (2.5,0.2); % Right arrow (top)
        \draw[->, thick, green] (-0.2,0.8) -- (-0.5,0.8); % Left arrow (bottom)
        % Deformation effect (sheared rectangle)
        \draw[thick] (0.2,0.2) -- (1.8,0.2); % Top line
        \draw[thick] (0.2,0.8) -- (1.8,0.8); % Bottom line
        \draw[thick, dashed] (0.2,0.2) -- (0.2,0.8); % Left dashed line
        \draw[thick, dashed] (1.8,0.2) -- (1.8,0.8); % Right dashed line
        % Label
        \node[below] at (1,-0.7) {\textbf{Shear Stress}};
    \end{scope}

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    % Torsion
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \begin{scope}[xshift=3cm, yshift=-2cm]
        % Original shape (cylinder)
        \draw[thick] (0,0) ellipse (0.5 and 0.5);
        \draw[thick] (-0.5,0) -- (-0.5,-2);
        \draw[thick] (0.5,0) -- (0.5,-2);
        \draw[thick] (0,-2) ellipse (0.5 and 0.5);
        % Arrows for torsion
        \draw[->, thick, purple] (-0.7,-0.5) arc[start angle=180, end angle=90, radius=0.2]; % Left twist
        \draw[->, thick, purple] (0.7,-1.5) arc[start angle=0, end angle=-90, radius=0.2]; % Right twist
        % Deformation effect (twisted cylinder)
        \draw[thick, dashed] (0,-0.5) ellipse (0.5 and 0.5);
        \draw[thick, dashed] (0,-1.5) ellipse (0.5 and 0.5);
        % Label
        \node[below] at (0,-2.5) {\textbf{Torsion}};
    \end{scope}

    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    % Bending
    %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
    \begin{scope}[xshift=6cm, yshift=-3cm]
        % Original shape (beam)
        \draw[thick] (0,0) -- (2,0);
        \draw[thick] (0,-0.2) -- (2,-0.2);
        \draw[thick] (0,0) -- (0,-0.2);
        \draw[thick] (2,0) -- (2,-0.2);
        % Arrows for bending
        \draw[->, thick, orange] (1,0.5) -- (1,0.2); % Downward force
        \draw[->, thick, orange] (0.5,-0.5) -- (0.5,-0.2); % Upward force (left)
        \draw[->, thick, orange] (1.5,-0.5) -- (1.5,-0.2); % Upward force (right)
        % Deformation effect (bent beam)
        \draw[thick, decorate, decoration={snake, amplitude=2pt, segment length=10pt}] (0.2,0) -- (1.8,0);
        \draw[thick, decorate, decoration={snake, amplitude=2pt, segment length=10pt}] (0.2,-0.2) -- (1.8,-0.2);
        % Label
        \node[below] at (1,-0.7) {\textbf{Bending}};
    \end{scope}

\end{tikzpicture}

\end{document}
```

# Strain ($\epsilon$)
---
#AI
Strain is a measure of the deformation of a material caused by stress. It is a dimensionless quantity, representing the change in length relative to the original length.

**Formula:**
$$\qquad \epsilon = \dfrac{\Delta L}{L_0}$$
where;
$\epsilon$ is the strain (dimensionless, but sometimes expressed as m/m),
$\Delta L$ is the change in length ($L - L_0$),
and $L_0$ is the original length.

### Types of strain:

*   **Tensile Strain:**  Elongation due to tensile stress.
*   **Compressive Strain:** Shortening due to compressive stress.
*   **Shear Strain:**  Change in angle between initially perpendicular lines within the material due to shear stress.

# Young's Modulus (Y)
---
#AI 
Young's Modulus, also known as the modulus of elasticity, is a material property that describes its stiffness. It represents the relationship between stress and strain in the elastic region of the material's behavior.

**Formula:**

$\qquad Y = \dfrac{\text{Stress}}{\text{Strain}} = \dfrac{\sigma}{\epsilon}$

**Explanation:**

Young's Modulus indicates how much a material will deform (strain) under a given amount of stress. A higher Young's Modulus means the material is stiffer and requires more stress to produce a given amount of strain.  It's the slope of the linear portion of the stress-strain curve.

### Stress-Strain Curve:

```tikz
\usepackage{amsmath}
\begin{document}
\begin{tikzpicture}[scale=2, >=stealth]
    % Axes
    \draw[->, thick] (0,0) -- (6,0) node[right] {Strain ($\varepsilon$)};
    \draw[->, thick] (0,0) -- (0,5) node[above] {Stress ($\sigma$)};
    
    % Grid (optional)
    %\draw[gray!30] (0,0) grid (5.5,4.5);
    
    % Curve
    \draw[ultra thick, blue] (0,0) 
        -- (1.5,3) coordinate (elastic) 
        .. controls (2,3.2) and (2.5,3.5) .. (3,3.8) coordinate (ultimate)
        .. controls (3.5,3.5) and (4,2.5) .. (4.5,1.5) coordinate (fracture);
    
    % Key points
    \node[circle, fill=red, inner sep=2pt] at (elastic) {};
    \node[circle, fill=orange, inner sep=2pt] at (ultimate) {};
    \node[circle, fill=green!70!black, inner sep=2pt] at (fracture) {};

    % Young's Modulus Triangle
    \draw[red, dashed, thick] (0.5,1) -- (1.25,2.5) 
        -- (1.25,1) node[midway, right] {Rise ($\sigma_y$)} 
        -- cycle node[midway, below] {Run ($\varepsilon_y$)} ;
    \node[red,text width=1.5cm, align=center] at (0.5,2) {Young's Modulus};

    % Labels and annotations
    % Elastic region
    \draw[dashed] (1.5,3) -- (1.5,0) node[below] {$\varepsilon_y$};
    \draw[dashed] (1.5,3) -- (0,3) node[left] {$\sigma_y$};
    \node[text width=3cm, align=center] at (0.8,0.2) {Elastic region\\ (Linear behavior)};
    
    % Yield point
    \node[red, above] at (elastic) {Yield point\\ (Elastic limit)};
    
    % Ultimate tensile strength
    \draw[dashed] (3,3.8) -- (3,0) node[below] {$\varepsilon_u$};
    \draw[dashed] (3,3.8) -- (0,3.8) node[left] {$\sigma_u$};
    \node[orange, above] at (ultimate) {Ultimate tensile strength};
    
    % Fracture point
    \draw[dashed] (4.5,1.5) -- (4.5,0) node[below] {$\varepsilon_f$};
    \node[green!70!black, right] at (fracture) {Fracture point};
    
    % Plastic deformation region
    \node[text width=3cm, align=center] at (3.75,1.5) {Plastic deformation\\ (Permanent strain)};
    
    \node[text width=1.5cm, align=center] at (2.25,1.3) {Transition Region};
    
    % Strain hardening
    \draw[->, thick] (2.5,3.4) to (3,3.7) node[right] {Strain hardening};
    
    % Necking region
    \draw[->, thick] (3.6,3) to (4,2.3) node[right] {Necking};
\end{tikzpicture}
\end{document}
```



The relationship between stress and strain is often visualized using a stress-strain curve, which is unique for each material. Key regions and points on the curve include:

* **Elastic Region:** The initial linear portion of the curve.  Here, the material obeys Hooke's Law (stress is proportional to strain), and the deformation is reversible. If the stress is removed, the material returns to its original shape.
* **Yield Point:** The point where the material transitions from elastic to plastic behaviour. Beyond this point, some permanent deformation occurs.
* **Plastic Region:** The region where the material undergoes permanent deformation. Even if the stress is removed, the material will not fully return to its original shape.
* **Ultimate Tensile Strength:** The maximum stress the material can withstand before it starts to weaken.
* **Fracture Point:** The point where the material breaks.
* **Strain Hardening:** The increase of stress in the plastic region, where more and more stress is needed for the material to deform.
* **Necking:** The decrease of cross-sectional area, which happens locally on the material.

# Pressure (P)
---
#AI 
While stress describes internal forces within a solid object, pressure typically refers to the force exerted by a fluid (liquid or gas) on a surface.

### Formula:
$$\qquad P = \dfrac{F}{A}$$

where;
$P$ is the pressure (in Pascals (Pa)),
$F$ is the force exerted by the fluid (in Newtons (N)),
and $A$ is the area over which the force is distributed (in square meters ($m^2$)).

### Explanation:

Pressure is a scalar quantity (it has magnitude but no direction). It acts equally in all directions at a given point within a fluid.  The key difference between pressure and stress is that pressure usually refers to a force exerted *by* a fluid *on* a surface, while stress refers to internal forces *within* a solid material.

### Relationship between Stress and Pressure:

In some contexts, pressure can *cause* stress within a solid object. For example, if a solid object is submerged in a fluid under high pressure, the pressure will create compressive stress within the object.
