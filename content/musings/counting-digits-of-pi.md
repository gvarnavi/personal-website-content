---

date: 2022-07-25T14:00:00+06:00
lastmod: 2022-07-25T14:00:00+06:00
title: Counting Digits of Pi
authors: ["georgiosvarnavides"]
categories:
  - musings
slug: counting-digits-of-pi
comments: true
thumbnail: /images/musings-03.png
cover:
  image: /images/musings-03-cover.png
  alternate: London Underground 1933 Map Distorted Grid
  caption: Geographic map distortion overlaid on Harry Beck's 1933 London underground map  (see [[1]](https://community.wolfram.com/groups/-/m/t/2178322))
  style: full

---

## Introduction

As part of the MIT course 3.029 I taught in the spring of 2022, we held optional [coding "get-togethers"](https://dmse-mit.github.io/3029/docs/intro#want-more) once a week, alternating between "Data-Visualization Hour" and "Code Show and Tell".
In particular, the week of [Pi day](https://en.wikipedia.org/wiki/Pi_Day) happened to hall on "Code Show and Tell" and the students thought it'd be fun to code up one of the craziest Pi-related phenomena I know.

This is very beautifully explained in the [3Blue1Brown](https://www.youtube.com/c/3blue1brown) video below:

{{< youtube HEfHFsfGXjs >}}

## Mathematica SE solution

First, note that this exact question was [asked on the Mathematica SE in 2020](https://mathematica.stackexchange.com/questions/230170/perpectly-elastic-collision-pi-model) - with a very natural numeric solution using `DiscreteVariables` in `NDSolveValue`.

``` mathematica {style=friendly}
numericSolution[d_] := Module[{
   collisions = 0, m1 = 1, m2 = 100^(d - 1),
   x10 = 1, x20 = 2, v10 = 0, v20 = -1, tmax = 20,
   etot, newvelocity, vsol, sol
   },
  
  etot = m1 v10^2 + m2 v20^2;
  newvelocity[vv1_, vv2_] := Block[{tsol},
    tsol = 
     Quiet[Solve[{m1 vn1 + m2 vn2 == m1 vv1 + m2 vv2, 
        m1 vn1^2 + m2 vn2^2 == etot}, {vn1, vn2}]]; {vn1, vn2} /. 
     If[Sign[tsol[[1, 1, 2]]] != Sign[vv1], tsol[[1]], tsol[[2]]]
    ];
  
  sol = NDSolveValue[{
     x1'[t] == v1[t], x2'[t] == v2[t],
     x1[0] == x10, x2[0] == x20, v1[0] == v10, v2[0] == v20,
     WhenEvent[x1[t] == x2[t], {
       collisions += 1,
       vsol = newvelocity[v1[t], v2[t]],
       v1[t] -> vsol[[1]],
       v2[t] -> vsol[[2]]
       }],
     WhenEvent[x1[t] == 0, {
       collisions += 1,
       v1[t] -> -v1[t]
       }]},
    {x1, x2, v1, v2}, {t, 0, tmax}, DiscreteVariables -> {v1, v2}];
  Echo[collisions];
  sol
  ]
```
