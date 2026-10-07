---
layout: page
title: L1-norm minimisation for contact planning
description: SL1M, ICRA 2020 and RA-L 2021
img: assets/img/projects/sl1m.png
importance: 2
category: planning
---

**Steve Tonneau, Daeun Song, Pierre Fernbach, Andrea Del Prete, Michel Taïx, Nicolas Mansard and Young J. Kim**

_ICRA 2020 and RA-L 2021_

## Presentation

This project presents a line of work that aims at formulating the footstep planning problem, theoretically a combinatorial problem, into a continuous optimisation problem. The idea consists in formulating the original problem into a cardinality minimisation problem, relaxed into an L1-norm minimisation problem. The formulation, which we called SL1M, was first introduced in an ICRA publication, demonstrated in simulation with the Talos robot. It was then complemented with an RA-L paper. In this extension we studied in detail the limitations induced by the relaxation of the problem and showed empirically that those limitations could be mitigated efficiently by combining SL1M with a sampling-based contact planner. Our framework is shown to be up to two orders of magnitude faster than a pure Mixed Integer formulation of the problem, and preliminary results show that the formulation also applies to quadrupeds, with results on the quadruped ANYmal.

## Abstracts

### ICRA conference paper

One of the main challenges of planning legged locomotion in complex environments is the combinatorial contact selection problem. Recent contributions propose to use integer variables to represent which contact surface is selected, and then to rely on modern mixed-integer (MI) optimization solvers to handle this combinatorial issue. To reduce the computational cost of MI, we exploit the sparsity properties of L1 norm minimization techniques to relax the contact planning problem into a feasibility linear program. Our approach accounts for kinematic reachability of the center of mass (COM) and of the contact effectors. We ensure the existence of a quasi-static COM trajectory by restricting our plan to quasi-flat contacts. For planning 10 steps with less than 10 potential contact surfaces for each phase, our approach is 50 to 100 times faster than its MI counterpart, which suggests potential applications for online contact re-planning. The method is demonstrated in simulation with the humanoid robots HRP-2 and Talos over various scenarios.

### RA-L paper

One challenge of legged locomotion on uneven terrains is to deal with both the discrete problem of selecting a contact surface for each footstep and the continuous problem of placing each footstep on the selected surface. Consequently, footstep planning can be addressed with a Mixed Integer Program (MIP), an elegant but computationally-demanding method, which can make it unsuitable for online planning. We reformulate the MIP into a cardinality problem, then approximate it as a computationally efficient l1-norm minimisation, called SL1M. Moreover, we improve the performance and convergence of SL1M by combining it with a sampling-based root trajectory planner to prune irrelevant surface candidates.

Our tests on the humanoid Talos in four representative scenarios show that SL1M always converges faster than MIP. For scenarios when the combinatorial complexity is small (less than 10 surfaces per step), SL1M converges at least two times faster than MIP with no need for pruning. In more complex cases, SL1M converges up to 100 times faster than MIP with the help of pruning. Moreover, pruning can also improve the MIP computation time. The versatility of the framework is shown with additional tests on the quadruped robot ANYmal.

## Materials

**ICRA conference paper:** "SL1M: Sparse L1-norm Minimization for contact planning on uneven terrain"
[Paper]({{ '/assets/pdf/tonneau2020sl1m.pdf' | relative_url }}) &middot;
[Results video](https://youtu.be/gOQHI-YlOi0) &middot;
[Slides (ppt)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.pptx) &middot;
[Slides (pdf)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.pdf) &middot;
[Presentation video (mp4)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.mp4)

**RA-L paper:** "Solving Footstep Planning as a Feasibility Problem using L1-norm Minimization"
[Paper](https://hal.science/hal-03435135/document) &middot;
[YouTube video](https://youtu.be/tde1P7hLwsk)

BibTeX entries are available from the [publications](/publications/) page.

**Source code:** [github.com/loco-3d/sl1m](https://github.com/loco-3d/sl1m)

## Videos

**Presentation of the whole work at TUB**
{% include youtube.liquid id="qnvIrqgsW8U" title="Presentation of the whole work at TUB" %}

**RA-L submission results video**
{% include youtube.liquid id="3AfBM8K0wts" title="RA-L results video" %}

**Presentation of the work at ICRA**
{% include youtube.liquid id="yXZPpDD4sOU" title="Presentation of SL1M at ICRA" %}

**ICRA results video**
{% include youtube.liquid id="gOQHI-YlOi0" title="ICRA results video" %}
