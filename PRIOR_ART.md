# PRIOR ART

## Public Disclosure Timestamp
**Date:** February 22, 2026

This repository is a dated public disclosure of VORTEX architecture concepts.
Primary legal timestamp is the public GitHub commit history.

## Disclosed ideas (architecture-level)
- FPGA-mediated memory bridge between GPU-visible memory space and large DDR5 pools
- Bank switching model for extending effective GPU memory per node
- Rack-scale composition using standards-based PCIe + CXL class fabrics
- 8+1 topology concept (8 accelerator nodes + 1 fabric controller)
- Memory-capacity-first architecture tradeoff for LLM inference workloads
- Open publication strategy: prior art first, staged implementation release

## Explicitly withheld in this stage
- HDL/RTL source code
- exact hardware bill of materials and sourcing pipeline
- board-level schematics, layout, and SI/PI constraints
- implementation-specific firmware internals

## Initial publication commit
`Initial architecture concept - Prior Art publication 2026-02-22`
