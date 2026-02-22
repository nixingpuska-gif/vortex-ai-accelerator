# Fabric Topology Concept

## 8+1 composition
VORTEX rack composition uses:
- 8 accelerator nodes (compute + bridge + memory)
- 1 fabric controller board ("9th board")

The fabric controller composes nodes into one coordinated cluster domain.

## Functional roles
1. Node-to-node transport
   - Low-latency data movement for distributed inference.

2. Memory domain composition
   - Cluster-level visibility for distributed memory placement policies.

3. Control-plane coordination
   - Routing, health, and lifecycle orchestration hooks.

## Scale path
- Base unit: 8-node pod + 1 fabric controller.
- Expansion: multiple pods connected by higher-tier links.
- Software goal: keep cluster behavior consistent as pods are added.

## Architectural stance
Use standards-based fabric concepts (PCIe/CXL class) to avoid dependency on proprietary interconnect lock-in.
