---
layout: page
permalink: /software/
title: Software
description: The main software projects where I have significantly contributed or that I use extensively.
nav: true
nav_order: 4
---

## [The curves library](https://github.com/loco-3d/ndcurves) (now ndcurves)

This library started as a personal project and found its use within [MLP](https://github.com/loco-3d/multicontact-locomotion-planning), the multi-contact locomotion planning framework I used in my earlier work. A template-based library for creating curves of arbitrary order and dimension, eventually subject to derivative constraints. It comes with a Python implementation, and nice features such as variable control points, which allow you to automatically define and compute curves that optimally solve linear optimisation problems. Heavily used in MLP for end-effector trajectory optimisation, but also for centroidal dynamic trajectories (see [CROC](/projects/centroidal-trajectories/)).

## [SL1M](https://github.com/loco-3d/sl1m)

Implementation of the sparse L1-norm minimisation solver for multi-contact planning. See the [SL1M project page](/projects/sl1m/).
