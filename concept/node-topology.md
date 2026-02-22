# Node Topology Concept

## Objective
Define a single accelerator node that prioritizes inference memory capacity and operational density.

## Logical composition
A node is organized as:
- 4 GPU compute modules
- 4 memory-bridge modules (one bridge domain per GPU)
- Shared high-capacity DDR5 memory domain
- High-speed interconnect domain
- Unified thermal plate and service interfaces

## Data path (conceptual)
1. GPU issues memory request in native GPU address space.
2. Bridge translates request into extended memory-page mapping.
3. DDR5 domain serves data for active page window.
4. Data returns to GPU through the bridge path.

## Control path (conceptual)
- Driver/runtime controls page window selection.
- Health telemetry reports bridge, memory, and thermal state.
- Management plane coordinates policy and updates.

## Design principle
Treat each GPU plus bridge pair as an elastic memory domain that can be orchestrated across the full node.
