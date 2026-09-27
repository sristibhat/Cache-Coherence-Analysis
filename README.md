# Performance Analysis of Coherence Protocols for an 8-Core Tiled Architecture

## Project Overview

This project studies cache coherence in an 8-core tiled multicore architecture and proposes a neighbour-aware extension to the conventional MESI cache coherence protocol.

The proposed **MESI+IN** protocol introduces an additional **IN (In-Neighbour)** cache state. The state is intended to identify valid data available in a neighbouring cache so that data can be transferred directly between neighbouring caches when possible, reducing unnecessary communication and memory-access overhead.

## Objectives

- Study the conventional MESI cache coherence protocol in an 8-core tiled multicore architecture.
- Design an extension to MESI using an **IN (In-Neighbour)** state.
- Evaluate the baseline and proposed protocols using PARSEC benchmark applications.
- Analyse performance using IPC, CPI, AMAT, execution/simulation time, cache hit/miss rate, latency, and network traffic.

## System Configuration

| Component | Configuration |
|---|---|
| CPU | X86 Timing Simple CPU |
| Cores | 8 |
| Core frequency | 3 GHz |
| Main memory | 3 GB |
| L1 instruction/data cache | 64 KB per core |
| L2 cache | 256 KB per core |
| Benchmark suite | PARSEC |
| Selected benchmarks | Blackscholes, Bodytrack, Canneal, Dedup, Facesim |
| Simulator | gem5 |
| Memory system | Ruby |
| Baseline protocol | MESI |
| Proposed protocol | MESI+IN |
| Interconnection topology | SimplePt2Pt |

## Methodology

The baseline MESI protocol and the proposed MESI+IN protocol are evaluated under the same system configuration. The proposed mechanism uses neighbour locality to check whether requested data is available in a nearby cache before following the conventional coherence path.

The experiments use five PARSEC workloads:

- Blackscholes
- Bodytrack
- Canneal
- Dedup
- Facesim

## Performance Metrics

- Simulation time
- Simulated operations
- Simulated instructions
- Average host tick rate
- Instructions Per Cycle (IPC)
- Cycles Per Instruction (CPI)
- Cache hit rate
- Cache miss rate
- Average latency
- Network traffic
- Average Memory Access Time (AMAT)

## Results

The project report presents comparisons between the conventional MESI protocol and the proposed MESI+IN protocol across the selected PARSEC benchmarks.

The detailed graphs, measurements, methodology, diagrams, and discussion are available in [`docs/Project_Report.pdf`](docs/Project_Report.pdf).

## Future Scope

The report identifies **Mesh_XY** as a more scalable interconnection topology for future work. Other extensions discussed include larger many-core systems, adaptive routing, energy-aware communication, and evaluation with additional benchmark suites.

## Tools and Technologies

- C/C++
- gem5
- Ruby memory system
- PARSEC benchmark suite
- Cache coherence protocols
- Multicore computer architecture
- Network-on-Chip concepts

## Repository Contents

```text
MESI_IN_Cache_Coherence_Project/
├── README.md
├── docs/
│   └── Project_Report.pdf
├── results/
│   └── README.md
└── implementation/
    └── README.md
```

## Project Team

- Sristi Bhat
- Pavitra Kambar
- Saraswati Bhakta
- Aishwarya Kumbare

## Academic Project

Department of Electronics and Communication Engineering  
KLE Technological University, Hubballi  
Semester VI, 2025–2026
