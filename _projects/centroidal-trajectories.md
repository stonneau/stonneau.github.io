---
layout: page
title: Centroidal trajectory generation as a feasibility problem
description: 2PAC (TOG 2018), CROC (IROS 2018) and C-CROC (T-RO 2020)
img: assets/img/projects/centroidal-trajectories.gif
importance: 3
category: planning
---

**Steve Tonneau, Pierre Fernbach, Andrea Del Prete, Michel Taïx, Julien Pettré and Nicolas Mansard**

_IROS 2018 and TOG 2018_

<img src="{{ '/assets/img/projects/centroidal-trajectories.gif' | relative_url }}" alt="Teaser: centroidal trajectories" style="max-width: 70%" />

## Abstract

This project presents a new kind of contribution to the centroidal trajectory generation problem. It originates from the need, in contact motion planning, to answer one essential question: how to choose the contact locations that will allow an avatar or a robot to perform a given locomotion task? This question needs to be addressed from the perspective of the geometric constraints of the avatar, but also from a dynamic point of view. It raises the primordial question of feasibility: how can I be sure that there exists a feasible motion connecting two given contact configurations?

In the context of global motion planning, this question must be answered as fast as possible, to be able to handle the combinatorial aspect of contact planning. We propose two kinds of contributions to the field.

First, we introduce a continuous formulation of the problem, based on a Bezier curve representation of the centroidal trajectories. The convexity properties of such curves allow us to guarantee that the constraints are satisfied all along the trajectories. This prevents the typical performance and accuracy issues that go along with discretized approaches.

Then, we present cases where the problem, which is non-linear, can be reformulated in a convex fashion, which is conservative but is NOT an approximation. Under this formulation, the problem of generating a feasible centroidal trajectory falls back to the simple issue of solving 3 Linear Programs.

The result is an extremely fast and reliable approach to generate valid centroidal trajectories. Three publications are associated with this project.

## Materials

**TOG journal.** The introductory paper, which only applies to the quasi-static case: "2PAC: two point attractors for center of mass trajectories in multi contact scenarios"
[Paper]({{ '/assets/pdf/tonneau2018pac.pdf' | relative_url }}) &middot;
[Video 1](https://youtu.be/PvOoMSlKoxE) &middot;
[Video 2](https://youtu.be/iD9JaV0LPyw)

**IROS 2018 conference paper.** A complementary approach for the dynamic case: "CROC: convex resolution of centroidal dynamics trajectories to provide a feasibility criterion for the multi contact planning problem"
[Paper]({{ '/assets/pdf/fernbach2018croc.pdf' | relative_url }}) &middot;
[Video](https://youtu.be/xmPrdAUOTa4)

**T-RO journal paper.** "C-CROC: continuous and convex resolution of centroidal dynamic trajectories for legged robots in multi-contact scenarios". A continuous version of CROC, thanks to a generic decomposition method that could apply to any centroidal method of the state of the art. If you read only one paper, you should read this one.
[Paper](https://hal.science/hal-01894869/document) &middot;
[Video](https://youtu.be/oKKlShZvcs4)

BibTeX entries are available from the [publications](/publications/) page.

**Source code:** [gitlab.com/stonneau/bezier_COM_traj](https://gitlab.com/stonneau/bezier_COM_traj)

## Videos

**TOG video 1 - results**
{% include youtube.liquid id="PvOoMSlKoxE" title="2PAC results video" %}

**TOG video 2 - overview**
{% include youtube.liquid id="iD9JaV0LPyw" title="2PAC overview video" %}

**IROS one-minute video**
{% include youtube.liquid id="xmPrdAUOTa4" title="CROC one-minute video" %}

**C-CROC video**
{% include youtube.liquid id="oKKlShZvcs4" title="C-CROC video" %}
