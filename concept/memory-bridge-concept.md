# Memory Bridge Concept

## Problem being solved
GPU-local high-bandwidth memory is fast but expensive per GB and capacity-limited for large-model inference.

## Concept
Use an FPGA bridge to present a stable GPU-visible memory window while mapping that window onto a larger DDR5 memory space.

## Bank switching model
- The GPU sees a fixed logical window.
- The bridge maintains page tables for a larger physical space.
- Runtime requests page-window switches based on model execution phase.

This is conceptually similar to virtual-memory windowing patterns: maintain locality for active tensors while backing the full model in a larger tier.

## Reliability and behavior (conceptual)
- Integrity checks in bridge path (for memory safety goals)
- Telemetry hooks for page miss rate and switch latency
- Policy tuning in software layer to reduce switch churn

## What is intentionally omitted
- protocol-level translation details
- timing closure strategy
- RTL/HDL design
- implementation-specific tuning
