# Architecture (Public Concept)

## One-line summary
VORTEX is an open architecture concept for rack-scale AI inference that targets much lower memory cost by combining commodity compute, FPGA memory bridging, and standards-based fabric composition.

## Core building blocks
1. Compute nodes
- Multi-GPU execution domains optimized for inference serving.

2. Memory bridge
- FPGA logic maps a fixed GPU-visible window onto a larger DDR5-backed space.
- Bank switching selects active memory pages with software coordination.

3. Node interconnect
- PCIe Gen5 class links for node-internal and peer data paths.

4. Fabric layer
- CXL-oriented topology concepts for multi-node composition and cluster-scale memory behavior.

5. Operations plane
- Driver/runtime policies for page placement and switching.
- Management plane for telemetry, lifecycle, and orchestration.

## Design philosophy
- Capacity-first for inference economics.
- Open standards over proprietary lock-in.
- Publish architecture prior art first; implementation details later.

## Companion documents
- `docs/architecture-overview.md`
- `concept/node-topology.md`
- `concept/memory-bridge-concept.md`
- `concept/fabric-topology.md`
