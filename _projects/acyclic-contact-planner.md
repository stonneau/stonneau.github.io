---
layout: page
title: An efficient acyclic contact planner for multiped robots
description: T-RO 2018 and ISRR 2015
img: assets/img/projects/acyclic-contact-planner.png
importance: 4
category: planning
---

**Steve Tonneau, Andrea Del Prete, Julien Pettré, Franck Multon, Chonhyon Park, Dinesh Manocha and Nicolas Mansard**

_T-RO and ISRR 2015_

<img src="{{ '/assets/img/projects/acyclic-contact-planner.png' | relative_url }}" alt="Teaser: acyclic contact planning" style="max-width: 90%" />

## Abstract

We present a contact planner for complex legged locomotion tasks: standing up, climbing stairs using a handrail, crossing rubble and getting out of a car. The need for such a planner was shown at the Darpa Robotics Challenge, where such behaviors could not be demonstrated (except for egress).

Current planners suffer from their prohibitive algorithmic complexity, because they deploy a tree of robot configurations projected in contact with the environment.

We tackle this issue by introducing a reduction property: the reachability condition. This condition defines a geometric approximation of the contact manifold, which is of low dimension, presents a Cartesian topology, and can be efficiently sampled and explored.

The hard contact planning problem can then be decomposed into two sub-problems: first, we plan a path for the root without considering the whole-body configuration, using a sampling-based algorithm; then, we generate a discrete sequence of whole-body configurations in static equilibrium along this path, using a deterministic contact-selection algorithm.

The reduction breaks the algorithm complexity encountered in previous works, resulting in the first interactive implementation of a contact planner (open source). While no contact planner has yet been proposed with theoretical completeness, we empirically show the interest of our framework: in a few seconds, with high success rates, we generate complex contact plans for various scenarios and two robots, HRP-2 and HyQ. These plans are validated either in dynamic simulations, or on the real HRP-2 robot.

## Materials

**T-RO journal.** I recommend reading this paper, which is the most exhaustive presentation of the approach: "An efficient acyclic contact planner for multiped robots"
[Paper](https://hal.science/hal-01267345/document) &middot;
[Video](https://stevetonneau.fr/files/publications/ijrr16/tonneau_et_al_tro.mkv)

**ISRR 2015 conference paper:** "A reachability-based planner for sequences of acyclic contacts in cluttered environments"
[Paper]({{ '/assets/pdf/tonneau2017reachability.pdf' | relative_url }}) &middot;
[ISRR 2015 video](https://youtu.be/LmLAHgGQJGA)

**Extension of the planner to dynamic cases** (by my PhD student Pierre Fernbach, with Michel Taïx): "A kinodynamic steering-method for legged multi-contact locomotion"
[Paper]({{ '/assets/pdf/fernbach2017kinodynamic.pdf' | relative_url }}) &middot;
[IROS 2017 video](https://stevetonneau.fr/files/publications/iros17/kinodynamic_steering_method_for_legged_multicontact_locomotion.mp4)

**Integration of the planner within a centroidal trajectory generator** (by Justin Carpentier et al.): "A versatile and efficient pattern generator for generalized legged locomotion"
[Paper](https://hal.science/hal-01203507/document)

Installation and technical details of the software can be found [here](https://stevetonneau.fr/files/publications/isrr15/tro_install.html).

BibTeX entries are available from the [publications](/publications/) page.

## Videos

**Technical report video**
{% include youtube.liquid id="BJCZXUccB0A" title="Technical report video" %}

**Execution of the plan on HRP-2 (30s)**
{% include youtube.liquid id="YjL-DBQgXwk" title="Execution of the plan on HRP-2" %}

**ISRR video**
{% include youtube.liquid id="LmLAHgGQJGA" title="ISRR 2015 video" %}
