---
title: 'DensePCE: Exact Pseudo-Clique Enumeration Optimization'
summary: Optimized exact pseudo-clique enumeration in C++ with FPCE pruning, CSR graph storage, and Turán-based clique seeding via EBBkC.
date: 2025-11-23
featured: true
links:
  - type: code
    url: https://github.com/samiulislam07/DensePCE
tags:
  - C++
  - Graph Algorithms
  - High-Performance Computing
---

DensePCE optimizes an exact pseudo-clique enumeration framework for large real-world graphs.

<!--more-->

## Overview

Pseudo-cliques are dense subgraphs that relax the strict all-pairs connectivity of a clique. Enumerating them exactly is expensive because the search space grows quickly with graph size. DensePCE reduces that cost through algorithmic pruning and implementation-level engineering.

## What I built

- **FPCE pruning strategies** integrated into the exact enumeration framework to cut unproductive branches early.
- **CSR-based graph storage** (compressed sparse row) for compact, cache-friendly adjacency access.
- **Intrusive bucket-based degree maintenance** so vertex degrees update in constant time during recursion.
- **Turán-based clique seeding via EBBkC**, which seeds the search with cliques to reduce recursion overhead.

Together these changes speed up enumeration on large real-world graphs.
