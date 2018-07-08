---
layout: post
title:  "Shooting from the Heap: Ultra-Scalable Static Analysis with Heap Snapshots"
date:   2018-07-10 12:58:29
categories: publications
---

[Shooting from the Heap: Ultra-Scalable Static Analysis with Heap Snapshots](http://www.nevillegrech.com/shootingfromtheheap-issta18.pdf)

## Abstract

Traditional whole-program static analysis (e.g., a points-to analysis that models the heap) encounters scalability problems for realistic applications.  We propose a "featherweight" analysis that combines a dynamic snapshot of the heap with otherwise full static analysis of program behavior. The analysis is extremely scalable, offering speedups of well over 3x, with complexity empirically evaluated to grow linearly relative to the number of reachable methods. The analysis is also an excellent tradeoff of precision and recall (relative to different dynamic executions): while it can never fully capture all program behaviors (i.e., it cannot match the near-perfect recall of a full static analysis) it often approaches it closely while achieving much higher (3.5x) precision.

## Download and Usage
This work is part of the [Doop pointer analysis framework](https://bitbucket.org/yanniss/doop). Please first follow the instructions for the installation of Doop. Doop automatically downloads [HeapDL](https://github.com/plast-lab/heapdl). The HeapDL page also contains instructions on how to produce heap dumps for both JVM and Android platforms, which are required in order to utilize the featherweight analysis we describe.

In order to invoke the featherweight analysis, you need to add the `--featherweight-analysis` flag, together with the `--heapdl` flag to your invocation of Doop, as follows:

```
./doop <your options> --featherweight-analysis --heapdl <heap dump file>
```





