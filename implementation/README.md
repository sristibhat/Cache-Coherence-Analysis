# Implementation

## Architecture

An 8-core tiled multicore architecture was implemented using the gem5 simulator with the Ruby memory system. Each core uses private L1 instruction and data caches along with an L2 cache.

## Cache Coherence Protocol

The conventional MESI protocol was extended by introducing an additional **IN (In-Neighbour)** state.

The IN state enables a processor to identify whether the required cache block is available in a neighbouring cache. If available, the data can be obtained directly from the neighbouring cache, reducing unnecessary memory accesses and communication latency. Otherwise, the normal MESI coherence mechanism is followed.

## Interconnection Topology

The experimental architecture uses the **SimplePt2Pt** interconnection topology for communication between components.

## Workloads

The implementation was evaluated using five PARSEC benchmarks:

- Blackscholes
- Bodytrack
- Canneal
- Dedup
- Facesim

## Evaluation

The conventional MESI and proposed MESI+IN protocols were compared using:

- IPC and CPI
- Cache hit and miss rate
- Average latency
- Network traffic
- Average Memory Access Time (AMAT)
- Simulation performance

## Tools

- gem5 Simulator
- Ruby Memory System
- PARSEC Benchmark Suite
- Python