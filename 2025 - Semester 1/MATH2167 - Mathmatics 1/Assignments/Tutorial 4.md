---
aliases:
  - Week 4
---
```tikz
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}
	\node at (2.5, 4.5) {z=a+i\cdot b};
    % Axes
    \draw[->] (-1,0) -- (5,0) node[right] {Re};
    \draw[->] (0,-1) -- (0,5) node[above] {Im};
    
    % Triangle with colored components
    \draw[thick,red] (0,0) -- (4,0) node[below] {$a$};
    \draw[thick,blue] (4,0) -- (4,3) node[right] {$b$};
    \draw[thick,yellow] (0,0) -- (4,3) node[left] {$r$};
    
    % Right angle marker
    \draw (3.8,0) -- (3.8,0.2) -- (4,0.2);
    
\end{tikzpicture}

\end{document}

```

$z=r\cos(\theta)+i\cdot r\sin(\theta)=r\text{cis}(\theta)$

Expressed as rectangular form: $z=a+ib$

$\sin(\theta)=\dfrac{b}{r}$
$\cos(\theta)=\dfrac{a}{r}$
$\tan(\theta)=\dfrac{b}{a}$

$|z|=r=\sqrt{ a^2+b^2 }$

**De-Moivre's Theorem:**
Used for vectors represented in polar form. 

$z^n=(r(\cos(\theta)+i\sin(\theta)))^n$
$= r^n(\cos(\theta)+i\sin(\theta))$

$z_{k}=\sqrt[n]{r }\cdot\text{cis}(\dfrac{\theta+2\pi k}{n})$
where $k$ is the root to be solved.

## Using the Pythagorean Theorem with polar coordinates

**Example Diagram:**
```tikz
\usepackage{tikz}
\usepackage{amsmath} % For \pi

\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (-3.5,0) -- (3.5,0) node[right] {Re};
  \draw[->] (0,-3.5) -- (0,3.5) node[above] {Im};

  % Circles
  \draw (0,0) circle (1);
  \draw[red] (0,0) circle (2);
  \draw[blue] (0,0) circle (3);

  % Labels for radii
  \node at (1.1,0) {$1$};
  \node at (2.1,0) {$2$};
  \node at (3.1,0) {$3$};

  % Optional: Add some angles to show polar coordinates
  \draw[dashed] (0,0) -- (3,{pi/4});
  \node[right] at (2.5,{pi/8}) {$\theta$};

  % Optional: Mark a point to visualize a complex number
  \filldraw[red] ({2*cos(60)},{2*sin(60)}) circle (2pt);
  \node[red, above right] at ({2*cos(60)},{2*sin(60)}) {$2e^{i\pi/3}$};

\end{tikzpicture}
\end{document}
```


### Question 1a:

$z^2-9=0$
$z^2=9$
$z=\pm3$

$z_{1}=3+0i, z_{2}=3-0i$

> [!NOTE] Finding $r$
> When finding r take the complex component from $z^2$
> eg. $z^2-9=0 \therefore z^2=9+0\cdot i$
> then find the magnitude with the Pythagorean Theorem

$z^2=9+0\cdot i$
$|z^2|=\sqrt{ 9^2+0^2 }$
$|z^2|=r=9$

using De-Moivre's Theorem:
$z^2=9\cdot\text{cis}(0+2\pi k)$
$z=\sqrt{ 9 }\cdot\text{cis}(2\pi k)$

use $k=0,1$

when $k=0$ 
$\therefore z=3\cdot\text{cis}(\pi\cdot0)$
   $z=3*1$

when $k=1$
$\therefore z= 3\cdot \text{cis}(\pi\cdot1)$
   $z=3\cdot(-1)$
   
### Question 1b:
$z^2+4=0$
$z= \sqrt{ 4\cdot-1 }$
$z=\pm2i$
$z_{1}=0+2i, z_{2}=0-2i$

finding $r$:
$(c)=-4+0i$
$|c|=\sqrt{ (-4)^2+(0)^2 }$
$=\sqrt{ 16+0 }$
$r=4$

### Question 1c:

$z^2=-5+12i$

finding $r$:
$r=\sqrt{ (-5)^2+12^2}$
   $=\sqrt{ 25+144 }$
   $=\sqrt{ 169 }$
   $= \pm13$



### Question 2b:
$z^2+8=0$
$z=\sqrt{ 8 \cdot-1 }$
$z=\sqrt{ 4\cdot2 }\cdot i$
$z=2 \sqrt{ 4 }\cdot i$
$z_{1}=$


### Question 2c:
$z^2+6z+58=0$

Find Determinate:

$\Delta=\text{Determinate}=b^2-4ac$
   $=6^2-4\cdot1\cdot58$
   $=36-232$
   $=-196$

using the Quadratic Equation:

$\dfrac{-b\pm \sqrt{ b^2 -4a\cdot c}}{2a}$

$z=\dfrac{-6\pm{\sqrt{ -196 }}}{2}$
   $=\dfrac{-6\pm14i}{2}$
   $=-3\pm7i$

### Question 2d:
$z^2-10z+29=0$

Find Determinate:

$\Delta=\text{Determinate}=b^2-4ac$
   $=(-10)^2-4\cdot1\cdot29$
   $=100-116$
   $=-16$

using the Quadratic Equation:

$\dfrac{-b\pm \sqrt{ b^2 -4a\cdot c}}{2a}$

$z=\dfrac{-6\pm{\sqrt{ -16 }}}{2}$
   $=\dfrac{-6\pm4i}{2}$
   $=-3\pm2i$

### Question 3a:
$2i$

$2i=\dfrac{0\pm \sqrt{ -8 }}{2}$
$\alpha=2i,\beta=-2i$
$z^2-(\alpha+\beta)z+\alpha\beta=0$

$z^2+4=0$

### Question 3b:
$-2,3$

$\alpha=-2, \beta=3$
$z^2-(\alpha+\beta)z+\alpha\beta=0$
$z^2-(-2+3)z+(-2)\cdot3=0$
$z^2-z-6=0$

### Question 3c:
$\alpha=-2+5i,\beta=-2-5i$
$z^2-(\alpha+\beta)z+\alpha\beta=0$
$z^2-((-2+5i)+(-2-5i))z+(-2+5i)\cdot(-2-5i)=0$
$z^2-(-4)z+(-2+5i)(-2-5i)=0$
$z^2-(-4)z+((-2)^2-(5i^2))=0$
$z^2+4z+29=0$