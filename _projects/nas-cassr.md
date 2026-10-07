---
layout: page
title: Global footstep planning
description: NAS (Humanoids 2024) and CASSR (ICRA 2026)
img: assets/img/projects/nas-cassr.jpg
importance: 1
category: planning
---

**NAS:** Jiayi Wang, Saeid Samadi, Hefan Wang, Pierre Fernbach, Olivier Stasse, Sethu Vijayakumar and Steve Tonneau<br />
**CASSR:** Jiayi Wang and Steve Tonneau

_Humanoids 2024 and ICRA 2026_

<img src="{{ '/assets/img/projects/nas-frames.jpg' | relative_url }}" alt="NAS: Talos in simulation (corridor, staircase) and on the real robot" style="max-width: 100%" />

## Presentation

Footstep planning is a combinatorial search problem: which surface each foot steps on, in what order, and where exactly on that surface. These two works tackle it from complementary angles, both with the humanoid robot Talos.

**NAS** computes _all_ the solutions to the contact planning problem in a given number of steps, which yields a globally optimal policy that can be queried in real time to plan the next footsteps. **CASSR** searches for a contact sequence with A\*, but propagates convex, continuous reachability constraints along the search instead of discretising them, which makes the search fast even with rotations.

## Abstracts

### NAS: N-step computation of all solutions to the footstep planning problem

How many ways are there to climb a staircase in a given number of steps? Infinitely many, if we focus on the continuous aspect of the problem. A finite, possibly large number if we consider the discrete aspect, i.e. on which surface which effectors are going to step and in what order. We introduce NAS, an algorithm that considers both aspects simultaneously and computes all the possible solutions to such a contact planning problem, under standard assumptions. To our knowledge NAS is the first algorithm to produce a globally optimal policy, efficiently queried in real time for planning the next footsteps of a humanoid robot. Our empirical results (in simulation and on the Talos platform) demonstrate that, despite the theoretical exponential complexity, optimisations reduce the practical complexity of NAS to a manageable bilinear form, maintaining completeness guarantees and enabling efficient GPU parallelisation. NAS is demonstrated in a variety of scenarios for the Talos robot, both in simulation and on the hardware platform. Future work will focus on further reducing computation times and extending the algorithm's applicability beyond gaited locomotion.

### CASSR: continuous A-Star search through reachability for real time footstep planning

<img src="{{ '/assets/img/projects/cassr-scenario.jpg' | relative_url }}" alt="CASSR: Talos planning a sequence of footsteps over stepping stones" style="max-width: 50%; float: right; margin: 0 0 1rem 1rem" />

Footstep planning involves a challenging combinatorial search. Traditional A\* approaches require discretising reachability constraints, while Mixed-Integer Programming (MIP) supports continuous formulations but quickly becomes intractable, especially when rotations are included. We present CASSR, a novel framework that recursively propagates convex, continuous formulations of a robot's kinematic constraints within an A\* search. Combined with a new cost-to-go heuristic based on the EPA algorithm, CASSR efficiently plans contact sequences of up to 30 footsteps in under 125 ms. Experiments on biped locomotion tasks demonstrate that CASSR outperforms traditional discretised A\* by up to a factor of 100, while also surpassing a commercial MIP solver. These results show that CASSR enables fast, reliable, and real-time footstep planning for biped robots.

<small>CASSR figure: Wang and Tonneau, arXiv:2603.02989, CC BY 4.0.</small>

## Materials

**NAS** (Humanoids 2024, Nancy, France)
[Paper (arXiv)](https://arxiv.org/pdf/2407.12962) &middot;
[Paper (HAL)](https://hal.science/hal-04730135/document) &middot;
[Video](https://youtu.be/I5yFe0ez0sI)

**CASSR** (ICRA 2026)
[Paper (arXiv)](https://arxiv.org/pdf/2603.02989) &middot;
[Video](https://youtu.be/reDGK-VXg9k)

BibTeX entries are available from the [publications](/publications/) page. CASSR continues the line of work on contact planning started with [SL1M](/projects/sl1m/).

## Videos

**NAS**
{% include youtube.liquid id="I5yFe0ez0sI" title="NAS: N-step computation of all solutions to the footstep planning problem" %}

**CASSR**
{% include youtube.liquid id="reDGK-VXg9k" title="CASSR: continuous A-Star search through reachability for real time footstep planning" %}
