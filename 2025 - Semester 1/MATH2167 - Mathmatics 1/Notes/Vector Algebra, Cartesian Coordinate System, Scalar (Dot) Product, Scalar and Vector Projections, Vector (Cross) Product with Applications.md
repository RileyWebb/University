
## Defining Terms:

- **Scalar Quantity:**  A value completely described by it's quantity (e.g. Distance, Speed, Time)
- **Vector Quantity:** A value described by both it's magnitude and direction (e.g. Displacement, Velocity)
- **Unit Vector:** A vector with a magnitude of 1


## Notation:

$R<i,j>$ - A vector from the origin, equivalent to $\vec{OR}$
$\underset{\sim}{a}$ or $\textbf{a}$ - Vector $a$
$\vec{AB}$ - Vector from point **A** to **B**
$|\underset{\sim}{a}|$ or $d(AB)$ or $|\vec{AB}|$ - Magnitude of vector **A** to **B** 
$\hat{\underset{\sim}{a}}$ - Unit vector
$\underset{\sim}{i}$, $\underset{\sim}{j}$ - $x$ and $y$ axis unit vectors respectively
$\vec{AB}+\vec{BA}=\vec{AA}=\underset{\sim}{O}$ - Zero vector
$\alpha$ is for the x-axis, $\beta$ is for the y-axis, $\gamma$ is for the z-axis

## Vector normalisation:
$\dfrac{\vec{AB}}{|\vec{AB}|} = A_{\text{norm}}$


If $A(x_1, y_1)$ and $B(x_2, y_2)$, then;
$\vec{OA} = x_1\cdot \underset{\sim}{i} + y_1 \cdot \underset{\sim}{j}$
$\vec{OB} = x_2\cdot \underset{\sim}{i} + y_2 \cdot \underset{\sim}{j}$

# Vector Operations
---

## Dot Product
Also know as **scalar product**.
$$\vec{a}\cdot\vec{b}=|\vec{a}||\vec{b}|\cos\theta$$
$$\cos\theta=\frac{\vec{a}\cdot\vec{b}}{|\vec{a}||\vec{b}|}$$
## Cross Product

$$\vec{a}\times \vec{b}=|\vec{a}||\vec{b}|\sin(\theta) n$$
where;
$\theta$ is the angle between $\vec{a}$ and $\vec{b}$,
$|\vec{a}|$ and $|\vec{b}|$ are the magnitudes of vectors $\vec{a}$ and $\vec{b}$,
$n$ is a unit vector perpendicular to the plane containing  $\vec{a}$ and $\vec{b}$.

**Matrix notation:**
$\vec{a}\times\vec{b} = \begin{bmatrix} i& j & k \\ a_{1} & a_{2} & a_{3} \\ b_{1} & b_{2} & b_{3}\end{bmatrix} = i\begin{bmatrix} a_{2} & a_{3} \\ b_{2} & b_{3}\end{bmatrix}+j\begin{bmatrix}a_{1}&a_{3}\\b_{1}& b_{3}\end{bmatrix} + k\begin{bmatrix}a_{1}&a_{2}\\b_{1}&b_{2}\end{bmatrix}$
```tikz
\begin{document}
\begin{tikzpicture} 
  \draw[thin,gray!40] (-2,-2) grid (2,2);
  \draw[<->] (-2,0)--(2,0) node[right]{$x$};
  \draw[<->] (0,-2)--(0,2) node[above]{$y$};
  \draw[line width=2pt,blue,-stealth](0,0)--(1,1) node[anchor=south west]{$\boldsymbol{u}$};
  \draw[line width=2pt,red,-stealth](0,0)--(-1,-1) node[anchor=north east]{$\boldsymbol{-u}$};
\end{tikzpicture}
\end{document}
```
```tikz
\begin{document}
\begin{tikzpicture}
  \draw[thin,gray!40] (-4,-4) grid (4,4);
  \draw[<->] (-4,0)--(4,0) node[right]{$x$};
  \draw[<->] (0,-4)--(0,4) node[above]{$y$};
\draw[line width=2pt,cyan,-stealth][->](0,0) -- (2,-3);
\end{tikzpicture}
\end{document}
```
