# VORTEX AI Accelerator
### Open Architecture for Democratizing AI Computing

> "The most advanced AI clusters costing $40,000 per board
> should cost $1,000-2,000. This is arithmetic, not fantasy."

## What is this?
An open hardware architecture concept for rack-scale AI inference clusters
that targets performance classes associated with NVIDIA DGX-style systems
at 10-40x lower cost per GB of AI memory.

## Key innovations (Prior Art - February 22, 2026)
- FPGA-based GDDR6X-to-DDR5 memory bridge (Bank Switching)
- 600GB+ effective VRAM per GPU node via server DDR5
- PCIe Gen5 + CXL 3.0 fabric (open alternative to proprietary interconnect stacks)
- Full-coverage copper cold plate thermal management
- Plug-and-play cluster management (Web GUI)

## Status: Architecture Design Phase
MVP target: Q3 2026

## Why open source?
Read [MANIFESTO.md](./MANIFESTO.md)

## Repository layout
- `PRIOR_ART.md` - legal timestamp and disclosed-idea list
- `docs/architecture.md` - public architecture summary
- `docs/architecture-overview.md` - extended high-level architecture concept
- `docs/problem-statement.md` - why market concentration blocks AI access
- `docs/comparison-nvidia.md` - comparative economics snapshot with charts
- `docs/roadmap.md` - staged roadmap
- `docs/prior-art-notice.md` - public timestamp and scope of disclosure
- `docs/prior-art-posts-2026-02-22.md` - ready-to-publish post drafts
- `concept/node-topology.md` - node topology in words
- `concept/memory-bridge-concept.md` - conceptual FPGA bridge model
- `concept/fabric-topology.md` - 8+1 fabric topology concept

## Disclosure boundary (current stage)
This repository intentionally excludes implementation-sensitive details such as:
- HDL/Verilog source
- exact part numbers and board routing files
- firmware flashing workflows
- full BOM and procurement strategy

Those details are planned for staged release after MVP milestones.
