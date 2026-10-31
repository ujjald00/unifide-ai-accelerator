# Proposed architecture

## Objective and scope

Design a memory-rich accelerator for recurring local inference and model adaptation. Evaluate a specific workload before selecting the compute, memory, package, fabric, or software configuration.

## Candidate components

The concept includes programmable tensor engines, vector/reduction capability, on-chip SRAM, a memory subsystem, host attachment, and a scale-up interconnect. Chiplet count and controller placement remain open until workload traffic, floorplan, and package evidence support a choice.

## Target register

| Item | Proposed target or decision | Evidence status |
| --- | --- | --- |
| Local memory | 128/256 GB; contingent 512 GB option | Design proposal; density and package feasibility unresolved |
| Memory route | Wide LPDDR baseline; evaluate a costed HBM alternative | No production route selected |
| Useful sustained local bandwidth | Approximately 1 TB/s | Unmeasured target |
| Scale-up | Up to eight modules | Topology and physical implementation unresolved |
| Endpoint bandwidth | 500 GB/s aggregate Tx + Rx | Unmeasured target; not system bisection bandwidth |
| Compute and power | Size from workload traces | No committed FLOPS or power specification |
| Protection | Evaluate ECC and reliability requirements | Implementation and overhead unresolved |
| Software | Define operators, numerical behavior, runtime and framework integration | Not implemented here |

If the endpoint target is symmetric, 500 GB/s combined means 250 GB/s transmit plus 250 GB/s receive. GB/s means gigabytes per second. Useful collective bandwidth, latency, contention, and bisection bandwidth need separate assessment.

Eight modules provide distributed memory. Their summed capacity is not automatically a single coherent memory pool.

## Workload priority

1. Local inference with a named model, context length, batch, precision, and quality requirement.
2. Parameter-efficient adaptation with a frozen recipe and explicit trainable parameters.
3. Bounded full-parameter training only after accounting for model state, activations, compute, communication, and convergence.

## Decisions still open

- Compute sizing and numerical support.
- Memory interfaces, controller placement, usable capacity, and protection overhead.
- Fabric topology, communication primitives, and sharding strategy.
- Package, board, thermal, power, test, and manufacturing feasibility.
- Compiler/runtime scope and operator coverage.
- Quote-backed complete-system economics.

No cost advantage, production readiness, frontier-training parity, or fabricated-device performance is established by this document.
