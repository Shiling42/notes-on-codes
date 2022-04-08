---
title: Mathematica
---
## Plot Tricks

### Theme with linestyle

```Mathematica
PlotTheme -> {"Scientific", "DashedLines"}
```

### Vertical lines in a plot

```mathematica
Epilog -> {Line[{{x0,y0}, {x1,y1}}]}
```

### Legend size

```mathematica
LabelStyle -> 
 Directive[FontFamily -> "Helvetica", Black, FontSize -> 15]
```

### Colorbar Legend

```mathematica
PlotLegends -> BarLegend[Automatic, LegendLabel -> "z"]
```

### Frame ticks and labels size

```mathematica
FrameStyle -> Directive[Black, FontSize -> 15]
```

### Unify and resize fig

```mathematica
Rasterize[,RasterSize -> 15]
```

### Latex input

```Mathematica
<< MaTeX`
MaTeX["\sin{x}"]
```

### Multiple figures in a single plot
```Mathematica
<< MaTeX`
Column@{
Row@{
}
}
```

## Math and Models 

### Basin of attraction

```Mathematica
tmax = 10;
tol = 0.01;
(*Solution to ODE that maps t to {x[t],y[t]}*)
sol[x0_?NumericQ, y0_?NumericQ, Req_, \[Eta]_] := 
  First@NDSolve[
     Evaluate[{x[0] == x0, y[0] == y0, 
       x'[t] == \[Eta] x[t]^2 ((1 - y[t] - x[t]) - Req x[t]) - x[t], 
       y'[t] == \[Eta] y[t]^2 ((1 - y[t] - x[t]) - Req y[t]) - 
         y[t]}], {x, y}, {t, 0, tmax}] /. 
   HoldPattern[{x -> xi_, y -> yi_}] :> Function[{t}, {xi[t], yi[t]}];
BasinAssign := Function[{f}, Norm[f[tmax]]];
Manipulate[
 Show[DensityPlot[
   BasinAssign[sol[x0, y0, 0.5, 10^log\[Eta]]], {x0, 0, 1}, {y0, 0, 
    1}, PlotPoints -> 20, PlotLegends -> Automatic, 
   PlotRange -> Full], 
  StreamPlot[{\[Eta] l^2 ((1 - d - l) - 0.5 l) - 
      l, \[Eta] d^2 ((1 - d - l) - 0.5 d) - d} /. \[Eta] -> 10^
     log\[Eta], {l, 0, 1}, {d, 0, 1}, FrameLabel -> {"[B]", "[C]"}], 
  ContourPlot[
   Evaluate[{0 == \[Eta] l^2 ((1 - d - l) - 0.5 l) - l, 
      0 == \[Eta] d^2 ((1 - d - l) - 0.5 d) - d} /. \[Eta] -> 10^
      log\[Eta]], {l, 0, 1}, {d, 0, 1}, PlotPoints -> 100, 
   MaxRecursion -> 2]], {{log\[Eta], 1}, .7, 2, 
  Appearance ->  "Labeled"}, {{Req, 0.5}, 0, 1, 
  Appearance ->  "Labeled"}]

```

## General tricks

### Rule and RuleDelayed

The "rule" replacement replace the variables after evaluated, however, the "ruledelayed" replace the variables and then the evaluation starts.

```Mathematica
In[3]:= {x, x, x} /. x :> RandomReal[]
{x, x, x} /. x -> RandomReal[]

Out[3]= {0.424537, 0.500212, 0.799267}

Out[4]= {0.541989, 0.541989, 0.541989}
```

### Joint string and variables

```mathematica
dTlist = Table[StringForm["\[CapitalDelta]T=``", i ], {i, 1, 3}];
```
