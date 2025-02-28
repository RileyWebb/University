

# Types of material properties

- **Mechanical**
	- Stresses (elastic deformation)
		- Shear (stress parallel to a surface)
		- Normal (perpendicular to a cross-section)
		- Longitudinal (stress that changes the length of a material)
		- Tensile (stress that increases the length of a body)
		- Compressive (stress that decreases the length of a body)
	- Strains (plastic deformation)
- **Thermal**
- **Electrical**
- **Optical**
- **Chemical**
- **Magnetic**
- **Acoustic**


# Stresses and Strains

**Stress:** $\dfrac{F}{A}$
**Strain:** $\dfrac{\Delta l}{l_{o}}$


Stainless steel at 11% chromium

**Example of a material under stress:**
```tikz
\usepackage{pgfplots}
\begin{document}

\begin{tikzpicture}
    \begin{axis}[
        axis lines=middle,
        xlabel={Strain},
        ylabel={Stress},
        xmin=0, xmax=0.3,
        ymin=0, ymax=250,
        xtick={0,0.1,0.2,0.3},
        ytick={0,100,200,300,400},
        grid=major,
        samples=100,
        domain=0:0.3
    ]
        % Continuous stress-strain curve
        \addplot[blue, thick, domain=0:0.3] {
            (x<=0.02) * (2000*x) + 
            ((x>0.02) && (x<=0.1)) * (2000*0.02) + 
            ((x>0.1) && (x<=0.25)) * (2000*0.02 + 500*(x-0.1)) + 
            ((x>0.25) && (x<=0.3)) * (200 - 800*(x-0.25))
        };
        
        % Labels
        \node[right] at (axis cs:0.015,30) {Elastic Region};
        \node[right] at (axis cs:0.06,80) {Yielding};
        \node[right] at (axis cs:0.15,150) {Strain Hardening};
        \node[above] at (axis cs:0.27,200) {Necking};
    \end{axis}
\end{tikzpicture}

\end{document}
```
