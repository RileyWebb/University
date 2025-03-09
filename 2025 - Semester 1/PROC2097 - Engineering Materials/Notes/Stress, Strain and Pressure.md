$\text{Stress }(\sigma)=\dfrac{\Delta L}{L_{0}}=\dfrac{\Delta A}{A_{0}}$
$\text{Strain }(\epsilon)=\dfrac{Stress}{Y}$
$\text{Young's Modulus }(Y)=\dfrac{Stress}{Strain}$
where;
$L$ is the length of the subject
and $A$ is the cross-sectional area of the subject


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
