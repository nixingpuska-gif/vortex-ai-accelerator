# Architecture Overview

## Scope
This document describes the VORTEX architecture at concept level only.
It intentionally omits implementation-sensitive details.

## Design goals
- Reduce cost per GB for inference-oriented AI clusters.
- Scale memory capacity without relying on premium stacked-memory packaging.
- Use open or broadly adopted standards where possible.
- Keep cluster operations reproducible and vendor-neutral.

## Node concept (single accelerator node)
A node combines four logical layers:

1. Compute layer
   - Multi-GPU compute group for tensor execution.

2. Memory bridge layer
   - FPGA bridge exposes an extended memory window to each GPU.
   - Bank switching maps a smaller GPU-visible address window onto a larger DDR5 pool.

3. Memory pool layer
   - Server-grade DDR5 provides high-capacity inference memory.
   - Architecture prioritizes capacity and affordability over peak on-package bandwidth.

4. Interconnect and thermal layer
   - PCIe Gen5-based node interconnect and peer traffic.
   - Full-coverage cold plate thermal design for high sustained load.

## Cluster concept (rack scale)
- 8 accelerator nodes are composed through a dedicated fabric controller ("9th board" role).
- CXL-enabled memory semantics are used conceptually for pooled addressing and coherency models.
- A host management server coordinates scheduling, telemetry, firmware lifecycle, and deployment workflows.

## Software plane (conceptual)
- Bridge firmware layer handles memory-window translation and reliability functions.
- Kernel driver layer coordinates page switching and telemetry.
- Runtime allocator layer in ML stack places tensors according to memory locality and switching policy.

## Open items
- Exact protocol translation mechanics
- Runtime scheduling heuristics under mixed workloads
- Validation matrix for latency-sensitive inference patterns

## Not published in this document
- HDL/Verilog implementation
- exact silicon selections
- board-level schematics and routing constraints
- production BOM and sourcing details
