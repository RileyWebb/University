$\sin(\theta)=\dfrac{y}{\sqrt{ x^2+y^2 }}$
$\cos(\theta)=\dfrac{x}{\sqrt{ x^2+y^2 }}$
$\tan(\theta)=\dfrac{\sin(\theta)}{\cos(\theta)}$


### Question 1:
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

### Question 2:
> A vector has an x component of −25.0 units and a y component of 40.0 units. Find the magnitude and direction of this vector.

[[Tutorial problems 3-3-1.pdf#page=1&selection=40,0,52,28|Tutorial problems 3-3-1, page 1]]

$\sqrt{ (-25)^2+40^2 }= 5\sqrt{89}\approx 47.2$
$\tan(\theta)=\dfrac{40}{-25}$
$\theta=\tan^{-1}(\dfrac{40}{-25})=122^\circ$

### Question 8:
>  A rock is projected from the edge of the top of a building with an initial velocity of 12.2 m/s at an angle of 53º above the horizontal. The rock strikes the ground a horizontal distance of 25 m from the base of the building. Assume that the ground is level and that the side of the building is vertical. How tall is the building? (23.6 m)
#projectile_motion
[[Tutorial problems 3-3-1.pdf#page=1&selection=110,0,117,7|Tutorial problems 3-3-1, page 1]]

**Visualisation:**
```tikz
\usepackage{tikz}
\begin{document}

\begin{tikzpicture}

    % Axes
    \draw[->] (0,0) -- (8,0) node[right] {\textbf{x}};
    \draw[->] (0,0) -- (0,4) node[above] {\textbf{y}};

    % Trajectory
    \draw[thick, blue, domain=0:6, samples=50] plot (\x, {1.2*\x - 0.2*\x^2}) node[above right] {Trajectory};

    % Initial velocity vector
    \draw[->, red, thick] (0,0) -- (2,2.4) node[above left] {\textbf{V}};

    % Velocity components at launch
    \draw[->, red, dashed] (0,0) -- (2,0) node[below] {\textbf{$V_x = V \cos\theta$}};
    \draw[->, red, dashed] (2,0) -- (2,2.4) node[right] {\textbf{$V_y = V \sin\theta$}};

    % Intermediate velocity vectors
    \foreach \x in {1,3,5} {
        \pgfmathsetmacro\y{1.2*\x - 0.2*\x^2}
        \pgfmathsetmacro\vy{1.2 - 0.4*\x}
        \draw[->, thick] (\x,\y) -- ++(1.2, \vy);
        \draw[->, dashed] (\x,\y) -- ++(1.2,0);
        \draw[->, dashed] (\x,\y) -- ++(0,\vy);
    }

    % Angle theta
    \draw[thick] (0.8,0) arc[start angle=0,end angle=50,radius=0.8cm];
    \node at (1,0.3) {\textbf{$\theta$}};

\end{tikzpicture}

\end{document}

```

$\Delta x= 25\text{ m}$
$t=\dfrac{25}{12.2\cdot \cos(53^\circ)}\approx3.405\text{ s}$

$\Delta y=u_{y}\cdot t-\dfrac{1}{2}g\cdot t^2$
$\Delta y=12.2\sin(53^\circ)\cdot 3.405-\dfrac{1}{2}9.8\cdot 3.405^2=-23.6346\text{ m}$

### Question 9:
> A placekicker must kick a football from a point 36.0 m from the goal. The crossbar is 3.05 m high. When kicked, the ball leaves the ground with a speed of 20.0 m/s at an angle of 53° to the horizontal. 
> (a) By how much the ball clear or fall short of clearing the crossbar? 
> (b) Does the ball approach the crossbar while still raising or while falling?
#projectile_motion 
[[Tutorial problems 3-3-1.pdf#page=2&selection=10,0,21,1|Tutorial problems 3-3-1, page 2]]

**Visualisation:**
```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}

\begin{tikzpicture}[scale=0.25]
    % Axes
    \draw[->] (0,0) -- (40,0) node[right] {\textbf{x (m)}};
    \draw[->] (0,0) -- (0,10) node[above] {\textbf{y (m)}};

    % Trajectory curve
    \draw[thick, blue, domain=0:39, samples=100] 
        plot (\x, {(\x * tan(53)) - (9.81 * \x^2) / (2 * 20^2 * cos(53)^2)}) 
        node[above right] {\textbf{Trajectory}};

    % Kicking point
    \filldraw[red] (0,0) circle (0.5) node[below left] {Kick (0,0)};

    % Goalpost and crossbar
    \draw[thick] (36,0) -- (36,3.05) node[below left] {\textbf{Crossbar}};
    \draw[thick] (36,3.05) -- (37,3.05); % Small horizontal line at the top of the post

    % Initial velocity vector
    \draw[->, red, thick] (0,0) -- (6,8) node[above left] {\textbf{V = 20 m/s}};
    \draw[dashed, red] (0,0) -- (6,0) node[below] {\textbf{$V_x = V \cos 53^\circ$}};
    \draw[dashed, red] (6,0) -- (6,8) node[below right] {\textbf{$V_y = V \sin 53^\circ$}};

    % Angle theta
    \draw[thick] (3,0) arc[start angle=0,end angle=53,radius=3cm];
    \node at (3.5,1) {\textbf{$53^\circ$}};

    % Dotted line to show goal height check
    \draw[dashed] (36,0) -- (36,6); % Extends to max height
    \filldraw[] (36, {36*tan(53) - (9.81*36^2)/(2*20^2*cos(53)^2)}) circle (0.4) node[right] {\textbf{Ball at x=36}};

\end{tikzpicture}

\end{document}

```

$u_{x}=20\cdot \cos(53^\circ)$
$u_{y}=20\cdot \sin(53^\circ)$

$\therefore$ $t=\dfrac{36}{20\cdot \cos(53^\circ)}\approx 2.99\text{ s}$
**Part a:**
using $s=ut+\dfrac{1}{2}at^2$:
$s=(20\cdot \sin(53^\circ))\cdot2.99-\dfrac{1}{2}9.8\cdot (2.99)^2\approx 3.951\text{ m}$
**Part b:**
using $v=u+at$:
$v=20\cdot \sin(53^\circ)-9.8\cdot2.99\approx-13.3293\text{ m/s}$

### Question 10:
> An airplane, whose air speed is 600 km/h, is supposed to fly in a straight path 35° North of East. But a steady 100 km/h wind is blowing from the north. In what direction should the plane head?
#projectile_motion 
[[Tutorial problems 3-3-1.pdf#page=2&selection=25,0,27,94|Tutorial problems 3-3-1, page 2]]

**Visualisation:**
```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}

\begin{tikzpicture}[scale=0.1]
    % Axes
    \draw[->] (0,0) -- (70,0) node[right] {\textbf{East}};
    \draw[->] (0,-20) -- (0,50) node[above] {\textbf{North}};

    % Airplane's airspeed vector (heading)
    \draw[->, thick, red] (0,0) -- (44.1,40.8) node[above right] {\textbf{Airplane Heading (600 km/h)}};
    
    % Wind velocity vector
    \draw[->, thick, blue] (44.1,40.8) -- (44.1,30.8) node[right] {\textbf{Wind (100 km/h)}};

    % Resultant velocity (actual path of the airplane)
    \draw[->, thick, green] (0,0) -- (44.1,30.8) node[below right] {\textbf{Actual Path (35° N of E)}};

    % Angle for heading
    \draw[thick] (10,0) arc[start angle=0,end angle=42.8,radius=10];
    \node at (12,4) {\textbf{42.8°}};

    % Angle for actual path
    \draw[thick] (10,0) arc[start angle=0,end angle=35,radius=10];
    \node at (15,3) {\textbf{35°}};

    % Labels
    \node at (22,-2) {\textbf{East}};
    \node at (-2,45) {\textbf{North}};
    
\end{tikzpicture}

\end{document}

```
