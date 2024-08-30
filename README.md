# LaTeX-AbqScale
LaTeX style file to include the FE-software Abaqus' rainbow and black-white scale

- Package to create ABAQUS scales with 10/12/14/16 colors and equally spaced values.
- Depending on preference the command can be used for all gradations or just minmax-values
- command usage: arg1=max, arg2=min, arg3=Title, arg4=scaling_factor-global, arg5=scaling_factor-boxwidth
- if box around scale and corresponding values is desired, use box-option: \usepackage[box]{abqscale}
- for german documents (using comma instead of dot as delimiter) import via \usepackage[german]{abqscale}
- font size option prepared but not inserted as it can be varied within the document by {\footnotesize \abqscalenumber{}{}{}{}{} }

\usepackage{abqscale} --> english typesetting, no frame
\usepackage[box]{abqscale} --> english typesetting, frame
\usepackage[german]{abqscale} --> german typesetting, no frame
\usepackage[german, box]{abqscale} --> german typesetting, frame

\abqscale*number*{*maximum value*}{*minimum value*}{*title*}{*general scaling factor*}{*frame width scaling*}

- vertical scale
  - 10 colors
    - ``\abqscaleten{10.0}{-10.0}{test}{1}{1}``
    - ``\abqscaletenminmax{10.0}{-10.0}{test}{1}{1}``
  - 12 colors
    - ``\abqscaletwelve{10.0}{-14.0}{Reaction Force RF3}{1}{1}``
    - ``\abqscaletwelveminmax{10.0}{-14.0}{Reaction Force RF3}{1}{1}``
  - 14 colors
    - ``\abqscalefourteen{10.0}{-18.0}{Displacement U1}{1}{1}``
    - ``\abqscalefourteenminmax{10.0}{-18.0}{Displacement U1}{1}{1}``
  - 16 colors
    - ``\abqscalesixteen{10.0}{-22.0}{S. Max. Principal}{1}{1}``
    - ``\abqscalesixteenminmax{10.0}{-22.0}{S. Max. Principal}{1}{1}``
  - black and white 10 steps
    - ``\abqscaletenminmaxbw{10.0}{-10.0}{test}{1}{1}``
- horizontal scale
  - 10 colors
    - ``\abqscaletenminmaxhorizontal{10}{0}{title}{1}{1}``
- continuous vertical scale
  - rainbow
    - ``\abqcontinuousscaleminmax{10}{0}{title}{1}{1}``
  - black and white
    - ``\abqcontinuousscaleminmaxbw{10}{0}{title}{1}{1}``
- continuous horizontal scale
  - rainbow
    - ``\abqcontinuousscaleminmaxhorizontal{10}{0}{title}{1}{1}``
  - black and white
    - ``\abqcontinuousscaleminmaxhorizontalbw{10.0}{-10.0}{test}{1}{1}``


Usage recommendation to place it anywhere in the figure:
```
\begin{figure}[h!tp]
  \begin{tikzpicture}
    \node at (0,0) {\includegraphics[width=0.5\textwidth]{pathtofigurewithoutscale.pdf}};
    \node at (-5,-2) {\abqscale*number*{*maximum value*}{*minimum value*}{*title*}{*general scaling factor*}{*frame width scaling*}};
  \end{tikzpicture}
\end{figure}
```
