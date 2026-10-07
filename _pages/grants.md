---
layout: page
permalink: /grants/
title: grants
description: Funded projects I have been involved in, with their results, and the awards that came with them.
nav: true
nav_order: 6
---

## Awards

- **Étoiles de l'Europe** (2022), French Ministry of Higher Education and Research, for the H2020 project MEMMO. The prize rewards the coordinators of successful collaborative European research projects; it was handed to the MEMMO coordinator, Nicolas Mansard, at the Musée du quai Branly, Paris, on 6 December 2022. [Announcement](https://www.actuia.com/actualite/robotique-nicolas-mansard-coordinateur-du-projet-memmo-laureat-des-etoiles-de-leurope/).
- **Grand Prix du numérique de l'ANR** (2016), for the ANR project ENTRACTE. Awarded at the 2nd _Rencontres du numérique de l'ANR_ (16-17 November 2016) to the coordinator, Nicolas Mansard, and presented by Antoine Petit, then CEO of Inria. [ANR report](https://anr.fr/fr/agenda/presentation-des-precedents-colloques/retour-sur-la-2eme-edition-des-rencontres-du-numerique-de-lanr/), [prize brochure](https://anr.fr/fileadmin/documents/2016/ANR_Prix-du-Numerique_BD.pdf).
- **RSI Exchanges Award** (2018): funded a total of six months of mobility between the University of Edinburgh and LAAS-CNRS (France) during my post-doc.

## Projects

### MEMMO: Memory of Motion (H2020, 2018-2022)

European project (Horizon 2020, grant [780684](https://cordis.europa.eu/project/id/780684)), from 1 January 2018 to 30 June 2022, coordinated by Nicolas Mansard (LAAS-CNRS) with ten partners. EU contribution: 3.96 M&euro;. I was a principal investigator on the project.

MEMMO aims at generating complex movements for robots with any combination of arms and legs interacting with a dynamic environment in real time. The approach rests on optimal control: massive amounts of optimal motions are pre-computed offline and compressed into a "memory of motion", which is recovered during execution and adapted to new situations with real-time model predictive control.

**Results**
- **Crocoddyl**, the open-source optimal control framework for multi-contact locomotion and manipulation: [github.com/loco-3d/crocoddyl](https://github.com/loco-3d/crocoddyl).
- 20 deliverables and 81 conference papers (figures from the [CORDIS results page](https://cordis.europa.eu/project/id/780684/results)).
- Three demonstrators: a humanoid robot (TALOS) performing locomotion and industrial tooling tasks for aircraft assembly, an exoskeleton walking with a paraplegic patient, and a quadruped robot doing an inspection task at a real construction site.
- A class on building a contact planner, given at the MEMMO winter school: see [presentations](/presentations/).

**Award:** [Étoiles de l'Europe](#awards) (2022).

### ENTRACTE: Understanding and planning anthropomorphic action (ANR, 2013-2017)

French national project ([ANR-13-CORD-0002](https://anr.fr/Projet-ANR-13-CORD-0002), programme CONTINT 2013), from October 2013 for 42 months, coordinated by Nicolas Mansard (LAAS-CNRS) with Inria Rennes - Bretagne Atlantique (Mimetic team). ANR funding: 688 228 &euro;. I worked on it first as a PhD student at IRISA and then as a post-doc at LAAS-CNRS (2015-2018).

ENTRACTE studied the mathematical foundations of movement generation, by conducting in parallel research on motion planning algorithms and research on the invariants of human movement, with the goal of controlling humanoid robots and animating virtual avatars. My contribution is the contact planning line of work: [An efficient acyclic contact planner for multiped robots](/projects/acyclic-contact-planner/) (T-RO), its [ISRR 2015](/publications/) predecessor, and [Character contact re-positioning under large environment deformation](/publications/) (Computer Graphics Forum).

**Results:** according to the [ANR prize brochure](https://anr.fr/fileadmin/documents/2016/ANR_Prix-du-Numerique_BD.pdf), the project led to 10 publications and 20 conference papers, including 3 in IEEE Transactions on Robotics, 1 in Computer Graphics Forum (Eurographics) and 2 in Communications of the ACM (one of them on the magazine cover), and to the organisation of two workshops, an IJCAI tutorial and an international conference in Toulouse. The project also ran a [fall school](https://gepettoweb.laas.fr/index.php/Teach/EntractFallSchool).

**Award:** [Grand Prix du numérique de l'ANR](#awards) (2016).

## Other roles

- Deputy director of the UKRI AI [CDT in Dependable and Deployable AI for Robotics](https://www.cdt-d2air.uk/) (CDT-D2AIR) since 2024. The CDT is [recruiting](/news/2026-10-07-cdt-d2air-recruiting/).
