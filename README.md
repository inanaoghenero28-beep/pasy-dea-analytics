# pasy-dea-analytics

**DEA-Based Performance Analytics for Isolated Industrial Operations**  
Companion repository to a peer-reviewed research paper and public content series.

---

## Research Disclosure

This repository accompanies:

> **"Performance Modeling for Isolated Industrial Operations: A Data Envelopment Analysis Framework"**  
> *Oghenero Orevaoghene Inana — Adlore Business Enterprise Limited*  
> Currently under review at **Operations Research Forum, Springer Nature**

A preprint is publicly available:  
**Research Square:** https://doi.org/10.21203/rs.3.rs-7930805/v1


Specific empirical results from the paper will be shared upon acceptance and publication.  
All notebooks in this repository use **fictional toy data only**.

---

## What This Repository Contains

Jupyter notebooks that accompany a public content series on DEA-based performance
analytics. Each notebook is a standalone, fully commented implementation designed
for readers with no assumed Python knowledge. The series demonstrates how
industrial engineers can apply quantitative analytics methods to real operational
problems.

---

## The Problem This Work Addresses

Conventional benchmarking — including Data Envelopment Analysis (DEA) — requires
multiple comparable facilities to construct an efficiency frontier. In many
real-world industrial settings, those comparators do not exist:

- Upstream oil and gas assets operating in isolation
- Remote mine sites with no peer facilities
- Pilot plants or prototype systems not yet replicated elsewhere
- Facilities where peer data is restricted by confidentiality

When peers are absent, DEA becomes infeasible. The frontier cannot be constructed.
The method — sound in every other respect — has nothing to compare against.

**PASy (Pernage Analytics System)** addresses this by reconstructing the
benchmarking environment from a single observed facility's own operating data,
enabling bounded DEA evaluation without external comparators.

---

## Notebooks

| # | File | Companion Article | Status |
|---|------|-------------------|--------|
| Index | `00_repository_index.ipynb` | Repository overview and environment check | ✓ Live |
| 1 | `01_dea_fundamentals.ipynb` | *What DEA Measures and Why Isolated Facilities Break It* | 
| 2 | `02_synthetic_dmu_generation.ipynb` | *Building a Benchmark from Nothing — The Synthetic DMU Idea* |TBD |
| 3 | `03_reference_set_construction.ipynb` | *TBD — Learning-Stack Applied Piece* |TBD |
| 4 | `04_pasy_template.ipynb` | *TBD — Practitioner Template* |TBD |

Notebooks are added as each companion article is published.  
Follow the author on LinkedIn for publication updates.

---

## Repository Structure

```
pasy-dea-analytics/
│
├── notebooks/
│   ├── 00_repository_index.ipynb       ← Start here — overview and environment check
│   ├── 01_dea_fundamentals.ipynb       ← Worked DEA example
│   ├── 02_synthetic_dmu_generation.ipynb   ← |TBD |
│   ├── 03_reference_set_construction.ipynb ← |TBD |
│   └── 04_pasy_template.ipynb          ← |TBD |
│
├── data/
│   └── README.md                       ← Toy datasets (fictional only, added with notebooks)
│
├── docs/
│   └── README.md                       ← Article links and supporting documentation
│
└── README.md                           ← This file
```

---

## The PASy Framework (Overview)

PASy integrates four components into a synthetic benchmarking pipeline:

**PRISM** — A domain classification scheme that organises operational variables
into five functionally distinct categories: Production, Resource, Internal
Operations, Supply Chain, and Monitoring. Each variable is assigned to exactly
one domain before synthetic generation begins.

**AHP (Analytic Hierarchy Process)** — Expert-based weighting of three variable
attributes: Controllability, Operational Impact, and Variability. These weights
produce a composite multiplier governing how much each variable is allowed to
deviate in synthetic scenarios.

**Beta-distributed perturbation** — A bounded stochastic process that generates
realistic synthetic peer DMUs. The Beta distribution is used because it is bounded,
flexible, and can be calibrated to reflect observed operational variability. All
synthetic values are subject to physical feasibility constraints.

**Bounded DEA** — Efficiency is evaluated against both an optimistic frontier
(best-case synthetic peers) and a pessimistic frontier (worst-case synthetic peers).
The geometric mean of the two scores provides a balanced, single-value efficiency
measure. Quartile classification converts the continuous score into four ordinal
performance bands for operational use.

Full methodology is documented in the companion paper (preprint link above).

---

## Content Series

This repository accompanies a LinkedIn content series titled  
**"You Can't Benchmark Without Peers - Or Can You?"**

The series connects each analytical method to a real operational problem —
demonstrating not what the tools do, but what they reveal when applied to
problems that matter in industrial practice.

Published articles are linked in `/docs/` as they go live.

---

## Tools and Environment

All notebooks run in **Google Colab** (no local installation required).  
Core dependencies:

```
numpy        — array operations and synthetic generation
pandas       — data handling and tabular output  
scipy        — Beta distribution sampling and statistical tests
matplotlib   — visualisation
ortools      — Google OR-Tools for DEA linear programming
```

Run `00_repository_index.ipynb` first to verify your environment.

---

## Author

**Oghenero Orevaoghene Inana**  
Industrial Operations Engineer | Performance Analytics | Researcher  
Adlore Business Enterprise Limited — Benin City, Nigeria  

**Contact:** frontdesk@adlorebusiness.ng  
**LinkedIn:** linkedin.com/in/oghenero-inana-98b224a3
**Research Square preprint:** https://doi.org/10.21203/rs.3.rs-7930805/v1

---

## Licence

This repository is shared for educational and research purposes.  
The PASy framework and its core implementation remain proprietary.  
Notebooks use fictional toy data and are intended for methodological
demonstration only.

For academic collaboration or research access enquiries:  
frontdesk@adlorebusiness.ng

---

*Repository created May 2026. Updated progressively as articles are published.*
