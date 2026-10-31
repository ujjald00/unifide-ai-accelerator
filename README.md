# UNIFIDE AI Accelerator

Open architecture documentation for a team-designed, memory-rich AI accelerator for local inference and model adaptation.

**Status as of October 30, 2026: architecture proposal and evaluation specification.** This repository contains documentation. It does not yet contain executable accelerator models, RTL, a compiler/runtime, an agent implementation, benchmark results, or fabricated silicon.

## Technical problem

We are investigating how to balance memory capacity and bandwidth, compute utilization, communication, power, and cost for specific inference and post-training workloads. Memory capacity alone does not establish useful performance or economic advantage.

## Proposed architecture

- Wide LPDDR memory as a baseline to evaluate against an HBM alternative.
- Programmable tensor/vector compute and on-chip SRAM.
- 128/256 GB local-memory options and a contingent 512 GB option.
- Scale-up across up to eight modules with distributed memory.
- Approximately 1 TB/s sustained useful local bandwidth as a design target.
- 500 GB/s aggregate transmit-plus-receive bandwidth per scale-up endpoint as a design target.

These are proposed specifications, not measured hardware capabilities. Chiplet count, memory-controller placement, compute throughput, power, packaging, ECC, and software support remain engineering decisions to resolve.

## Human design and agent support

Our human team defines the architecture, selects candidate configurations, interprets evidence, and makes engineering decisions. A proposed specialist-agent workflow would support evidence gathering, calculations, benchmark coordination, and cross-checks. That workflow is not implemented in this repository.

The initial evaluation scope is inference and parameter-efficient fine-tuning. Full-parameter training is secondary and requires an explicitly bounded recipe.

## Read the project

- [Architecture](ARCHITECTURE.md): components, targets, and unresolved decisions.
- [Evaluation plan](EVALUATION.md): reproducible workload and collective-evaluation protocol.
- [Implementation status](STATUS.md): what exists and what remains planned.

## ScienceClaw provenance

This repository was created for the ScienceClaw 3 Day Hackathon cohosted with Sundai, October 30–November 1, 2026. The architecture proposal and planning work predate the event. This initial publication packages that proposal; it does not represent a completed hackathon prototype. Later implementation and experimental results should be identified by their own commits and evidence.

## License

The original content published in this repository is available under the [MIT License](LICENSE). No third-party research papers, private UNIFIDE product source, credentials, or customer data are included.
