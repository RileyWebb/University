$\sin(\theta)=\dfrac{y}{\sqrt{ x^2+y^2 }}$
$\cos(\theta)=\dfrac{x}{\sqrt{ x^2+y^2 }}$
$\tan(\theta)=\dfrac{\sin(\theta)}{\cos(\theta)}$


**Question 1:**
> A surveyor measures the distance across a straight river by the following method: starting directly across from a tree on the opposite bank, she walks 100 m along the riverbank to establish a baseline. Then she sights across to the tree. The angle from her baseline to the tree is 35.0°. How wide is the river?

[[Tutorial problems 3-3-1.pdf#page=1&selection=29,0,36,8|Tutorial problems 3-3-1, page 1]]

```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[scale=0.03] % Adjust scale for better fit

  % Riverbank (baseline)
  \draw[thick] (0,0) -- (100,0) node[midway, below] {100 m};

  % Tree on opposite bank
  \coordinate (Tree) at (0,70); % Approximate river width (70 meters)
  \draw[thick] (0,0) -- (Tree);
  \draw[thick] (100,0) -- (Tree);

  % Angle
  \draw (100,0) -- (95,0); % Short line for angle
  \draw (95,0) arc (180:145:5); % Arc for angle
  \node[right] at (97,3) {$35^\circ$};

  % Label for river width
  \draw[dashed] (0,0) -- (0,70);
  \node[left] at (0,35) {w};

  % Tree symbol
  \draw[fill=green!50!black] (0,70) -- (-1,72) -- (1,72) -- cycle;
  \draw[fill=green!50!black] (0,72) -- (-1,74) -- (1,74) -- cycle;
  \draw[fill=green!50!black] (0,74) -- (-1,76) -- (1,76) -- cycle;
  \draw[thick, brown] (0,70) -- (0,68);
\end{tikzpicture}
\end{document}
```

$\tan(35^\circ)=\dfrac{w}{100}$
$w=100\cdot \tan(35^\circ)\approx70\text{ m}$

**Question 2:**
> A vector has an x component of −25.0 units and a y component of 40.0 units. Find the magnitude and direction of this vector.

[[Tutorial problems 3-3-1.pdf#page=1&selection=40,0,52,28|Tutorial problems 3-3-1, page 1]]

$\sqrt{ (-25)^2+40^2 }= 5\sqrt{89}\approx 47.2$
$\tan(\theta)=\dfrac{40}{-25}$
$\theta=\tan^{-1}(\dfrac{40}{-25})=122^\circ$

### Question 8:
>  A rock is projected from the edge of the top of a building with an initial velocity of 12.2 m/s at an angle of 53º above the horizontal. The rock strikes the ground a horizontal distance of 25 m from the base of the building. Assume that the ground is level and that the side of the building is vertical. How tall is the building? (23.6 m)

[[Tutorial problems 3-3-1.pdf#page=1&selection=110,0,117,7|Tutorial problems 3-3-1, page 1]]