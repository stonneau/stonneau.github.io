---
layout: page
permalink: /presentations/
title: Presentations
description: Talks and classes.
nav: true
nav_order: 5
---

## Talks

### How can model-based AI advance locomotion skills for legged characters? (keynote)

Keynote at [MIG 2023](https://project.inria.fr/mig2023/) (ACM SIGGRAPH Conference on Motion, Interaction and Games, Rennes, 15-17 November 2023), on the synergies between computer graphics and robotics at the age of massively parallel simulation.

{% include youtube.liquid id="3hqE37dCfhs" title="MIG 2023 keynote" %}

### The 'contact planning problem' for legged robots: a cardinality minimisation approach

In October 2020 I gave a presentation on our recent work with SL1M (see [below](#sl1m-sparse-l1-norm-minimization-for-contact-planning-on-uneven-terrain)) at [TUB](https://www.tu.berlin/). I was hosted by [Marc Toussaint](https://www.user.tu-berlin.de/mtoussai//index.html) and [Andreas Orthey](https://sites.google.com/view/aorthey/). I made a few mistakes, amended in the comments of the [YouTube video](https://www.youtube.com/watch?v=qnvIrqgsW8U).

[Slides (ppt)](https://stevetonneau.fr/files/presentations/tub20/tub20.pptx) &middot; [Slides (pdf)](https://stevetonneau.fr/files/presentations/tub20/tub20.pdf)

{% include youtube.liquid id="qnvIrqgsW8U" title="TUB talk: the contact planning problem for legged robots" %}

### SL1M: sparse L1-norm minimization for contact planning on uneven terrain

ICRA 2020 presentation of SL1M. See the [SL1M project page](/projects/sl1m/).

[Slides (ppt)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.pptx) &middot; [Slides (pdf)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.pdf) &middot; [Video (mp4)](https://stevetonneau.fr/files/presentations/sl1m/sl1m.mp4)

{% include youtube.liquid id="yXZPpDD4sOU" title="ICRA 2020 presentation of SL1M" %}

## Classes

### How to build a contact planner - H2020 Memmo winter school

Here is a video recorded at the end of January 2019. The class proposes an iterative approach to build a contact planner from scratch, with an end-result extremely close to HPP-rbprm. This class is part of a larger set of classes presented at the Memmo Winter school.

[Slides (odp)](https://stevetonneau.fr/files/classes/contact_planner/conctact_planner.odp) &middot; [Slides (pdf)](https://stevetonneau.fr/files/classes/contact_planner/contact_planner.pdf)

{% include youtube.liquid id="XUZIFw0NAm8" title="How to build a contact planner - Memmo winter school" %}

## Workshops

### Talos: status & progress (Humanoids 2020 workshop)

I co-organised this online workshop at the IEEE-RAS International Conference on Humanoid Robots ([Humanoids 2020](https://humanoids-2020.org/)) with Alexander Werner (University of Waterloo) and Olivier Stasse (LAAS-CNRS). It brought together the groups working on torque-controlled humanoid robots such as Talos, to compare control approaches and to discuss how to improve their dynamic capabilities. Six Talos robots exist in the world (PAL Robotics, LAAS, IJS, Waterloo, INRIA and Edinburgh), and the workshop was meant to start collaborations between these labs. The full programme is on the [workshop website](https://talos-humanoid.github.io/humanoids2020_workshop/).

**My talk: motion planning algorithms running on Talos** (interactive multi-contact planning for Talos). It presented two contributions: LEAS, a reinforcement learning framework that automatically plans guide paths for Talos in constrained environments (see [Learning to steer a locomotion contact planner](/publications/#chemin)), and [SL1M](/projects/sl1m/), a footstep planner that can be used reactively in challenging environments.
