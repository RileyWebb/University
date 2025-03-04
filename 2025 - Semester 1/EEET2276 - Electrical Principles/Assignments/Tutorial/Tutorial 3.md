```tikz
\usepackage{circuitikz}
\begin{document}

\begin{circuitikz} 
\ctikzset{european resistors}
    \draw
    (0,0) to[battery,v=$21V$] (0,4)
    to[R=$R_1$, v=$16V$] (3,4)
    to[R=$R_2$, v=$2V$] (6,4)
    to[R=$R_3$, v=$3V$] (9,4)
    -- (9,0) -- (0,0);
\end{circuitikz}
\end{document}
```

**Question 3:**
>  For the circuit shown use the voltage divider rule to determine the voltage between a and b.

[[Tut 02-c.pdf#page=3&selection=20,0,28,1|Tut 02-c, page 3]]
```tikz
\usepackage{circuitikz}
\begin{document}

\begin{circuitikz} 
    \draw
    (0,2) to[battery,v=$100V$] (0,5)
    to[european resistor=$10\Omega$] (3,5)
    to[european resistor=$22\Omega$] (6,5)
    node[anchor=south] {A}
    to[european resistor=$100\Omega$] (6,2)
    to[european resistor=$10\Omega$] (3,2)
    node[anchor=north] {B}
    to[european resistor=$12\Omega$] (0,2)
    -- (0,2);
\end{circuitikz}

\end{document}
```

**Total Resistance:** $R_{t}=10+22+100+10+12= 154\ohm$
**Resistance Between A and B:** $R_{ab}=100+10= 110\ohm$
**Voltage Between A and B:** $V_{ab}=\dfrac{110}{154}\cdot100=71.428\text{V}$


