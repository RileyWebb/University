[[Tutorial problems 2-1.pdf]]

**Question 1:**
> A car travels north at 30 m/s for one half hour. It then travels south at 40 m/s for 15 minutes. Find the total distance the car has travelled and its displacement

[[Tutorial problems 2-1.pdf#page=1&selection=31,0,35,61|Tutorial problems 2-1, page 1]]

Total Travel: $(30\cdot(30\cdot60)) + (40\cdot(15\cdot60))= 90000\text{m}$
Displacement: $(30\cdot(30\cdot60))-(40\cdot(15\cdot60))= 18000\text{m}$

**Question 2:**
> Wendy walks 10 m in one direction at 2 m/s, then runs 6 m in the same direction at 6 m/s. Next, she stops for 4 seconds, and finally walks in the opposite direction at 4 m/s for 6 seconds. What is Wendy’s average speed?

[[Tutorial problems 2-1.pdf#page=1&selection=39,0,59,25|Tutorial problems 2-1, page 1]]

Total Time: $\dfrac{10}{2} + \dfrac{6}{6} + 4 + 6 =16\text{ s}$
Total Distance: $10+6+6\cdot4=40\text{ m}$
Average Speed: $\dfrac{17.5}{40}=2.5\text{ m/s}$

**Question 3:**
> An automobile traveling along a straight road increases its speed from 30.0 m/s to 50.0 Okay, here are three follow-up questions based on the provided note, [[2025 - Semester 1/MANU2112 - Engineering Science/Assignments/Tutorial/Tutorial 3]],  worded as if you're asking me:

1.  In Question 8, you used the formula  $a=\dfrac{2(vt-s)}{2t}$. Can you remind me where this formula comes from, perhaps referencing the standard kinematic equations?

2.  For Question 10, the visualization shows the balls meeting. Is the y-axis in the graph representing the height above the ground, and could you clarify how the equations of motion for each ball were derived for the graph?

3.  In Question 11, the answer is given as a negative distance from the flagpole. Could you explain the significance of the negative sign in this context, and clarify where the runners meet relative to the flagpole?
m/s in a distance of 180 m. If the acceleration is constant, how much time elapses while the auto moves this distance?

[[Tutorial problems 2-1.pdf#page=1&selection=63,0,67,14|Tutorial problems 2-1, page 1]]

$t=\dfrac{2\cdot180}{30+50}= 4.5\text{ s}$

**Question 4:**
> An automobile manufacturer claims that its product will, starting from rest, travel 0.40 km in 9.0 s. What is the magnitude of the constant acceleration required to do this?

[[Tutorial problems 2-1.pdf#page=1&selection=71,0,74,71|Tutorial problems 2-1, page 1]]

$\dfrac{2\cdot400}{9^2}= 9.876 \text{ m/s}$

**Question 5:**
**A)** 1 & 7
**B)** 

**Question 6:**
**A)** 4
**B)** 5
**C)** a ball hitting a wall
**D)** a rocket

**Question 8:**
> A particle confined to motion along the x axis moves with constant acceleration from x = 2.0 m to x = 8.0 m during a 2.5-s time interval. The velocity of the particle at x = 8.0 m is 2.8 m/s. What is the acceleration during this time interval?

[[Tutorial problems 2-1.pdf#page=2&selection=66,0,88,43|Tutorial problems 2-1, page 2]]

**Visualisation:**
```tikz
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={$t$ (s)},
        ylabel={$x$ (m)},
        xmin=0, xmax=3,
        ymin=0, ymax=10,
        xtick={0, 1, 2, 2.5},
        ytick={0, 2, 4, 6, 8},
        grid=major,
        samples=100,
        domain=0:2.5
    ]
        % Quadratic function for motion (assuming constant acceleration)
        \addplot[blue, thick] {2 + 2.56*x + 0.64*x^2};
        
        % Points of interest
        \addplot[only marks, red, mark=*] coordinates {(0,2) (2.5,8)};
        
        % Labels
        \node[right] at (axis cs:0,2) {$x_0 = 2.0$};
        \node[right] at (axis cs:2.5,8) {$x_f = 8.0$};
    \end{axis}
\end{tikzpicture}

\end{document}
```

$t=2.5\text{ s}, v=2.8\text{ m/s}, s=6\text{ m}$

using $a=\dfrac{2(vt-s)}{2t}$
$\therefore \dfrac{2(2.8\cdot2.5-6)}{2.5^2}=0.32\text{ m/s}^2$


**Question 9:**
> A Cessna aircraft has a liftoff speed of 120 km/h. 
> 
> A) What minimum constant acceleration does the aircraft require if it is to be airborne after a takeoff run of 240 m? 
> B) How long does it take the aircraft to become airborne?

[[Tutorial problems 2-1.pdf#page=3&selection=11,0,11,50|Tutorial problems 2-1, page 3]]

- **A)** using $a=\dfrac{v^2-u^2}{2s}$
	 $\therefore \dfrac{(\dfrac{120}{3.6})^2}{2\cdot240}=2.31 \text{ m/s}$
- **B)** using $t=\dfrac{2s}{u+v}$
	 $\therefore \dfrac{2\cdot240}{\dfrac{120}{3.6}}=14.4\text{ s}$


**Question 10:**
> A ball is thrown upward from the ground with an initial speed of 25 m/s; at the same instant, another ball is dropped from a building 15 m high.
> 
> A) After how long will the balls be at the same height? 
> B) At what height do they meet?

[[Tutorial problems 2-1.pdf#page=3&selection=22,5,31,28|Tutorial problems 2-1, page 3]]

**Visualisation:**
```tikz
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={$t$ (s)},
        ylabel={$y$ (m)},
        xmin=0, xmax=3,
        ymin=-5, ymax=20,
        xtick={0,0.6,1,2},
        ytick={0,5,10,15,20},
        grid=major,
        samples=100,
        domain=0:2
    ]
        % Ball 1 (thrown upward)
        \addplot[blue, thick] {25*x - 4.9*x^2};
        
        % Ball 2 (dropped from 15 m)
        \addplot[red, thick] {15 - 4.9*x^2};
        
        % Intersection point at t = 0.6s, y = 11.4m
        \addplot[only marks, mark=*, black] coordinates {(0.6,13.236)};
        
        % Labels
        \node[blue, right] at (axis cs:0.1,3) {Thrown ball};
        \node[red, right] at (axis cs:1,10) {Dropped ball};
        \node[above] at (axis cs:0.6,13.236) {Meeting point};
    \end{axis}
\end{tikzpicture}

\end{document}
```

- **A)** $15-\dfrac{1}{2}9.8t^2=25\cdot t-\dfrac{1}{2}9.8t^2$
	$t≈0.6\text{ s}$
- **B)** $25\cdot0.6-\dfrac{1}{2}9.8\cdot0.6^2 \approx 13.236\text{ m}$

**Question 11:
> Runner A is initially 4.0 km west of a flagpole and is running with a constant velocity of 6.0 km/h due east. Runner B is initially 3.0 km east of the flagpole and is running with a constant velocity 5.0 km/h due west. How far are the runners from the flagpole when they meet?

[[Tutorial problems 2-1.pdf#page=3&selection=33,4,35,76|Tutorial problems 2-1, page 3]]

```tikz
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={$t$ (h)},
        ylabel={Distance from flagpole (km)},
        xmin=0, xmax=1,
        ymin=-5, ymax=5,
        xtick={0,0.4,0.8,1},
        ytick={-4,-2,0,2,3},
        grid=major,
        samples=100,
        domain=0:1
    ]
        % Runner A (moving east)
        \addplot[blue, thick] {-4 + 6*x};
        
        % Runner B (moving west)
        \addplot[red, thick] {3 - 5*x};
        
        % Intersection point at t = 0.4h, x = -1.6 km
        \addplot[only marks, mark=*, black] coordinates {(0.63,-0.18)};
        
        % Labels
        \node[blue, right] at (axis cs:0,-4) {Runner A};
        \node[red, right] at (axis cs:0,3) {Runner B};
        \node[above] at (axis cs:0.63,-0.18) {Meeting point};
    \end{axis}
\end{tikzpicture}

\end{document}

```


$-4+6\cdot t=3-5\cdot t$
$t=\dfrac{7}{11}$
$-4+6\cdot\dfrac{7}{11}=\dfrac{-2}{11}$


```tikz
\usepackage{pgfplots}

\begin{document}
  \begin{tikzpicture}[scale=2]
    \begin{axis}[
      title=Polar Coordinate Graph,
      grid=multiple,
      minor tick labels=false,
      width=12cm,
      height=8cm,
      axis x label= r,
      axis y label= θ (degrees),
    ]
      % Draw the circle
      \draw[domain=0:360, smooth] (\x rad) --
        coordinates {
          (0, 0)
          (\pi/2, 90)
          (\pi, 180)
          (\3\pi/2, 270)
          (2\pi, 360) % This repeats the start
        };
      \draw[domain=0:360, smooth] (\x rad) --
        coordinates {
          (0, 0)
          (\pi/2, 90)
          (\pi, 180)
          (\3\pi/2, 270)
          (2\pi, 360) % This repeats the start
        };
      \draw[domain=0:2] (0, --) (\pi/2, --) plot[domain=0:\pi/2] function
{sin(deg(\x))};
    }
    \begin{fill}
      circle (1cm);
    \end{fill}
  \end{tikzpicture}
\end{document}
```