# Evaluation plan

This document specifies planned work. No benchmark or simulation results are included in this initial repository.

## Freeze the experiment

For each experiment record the model and revision, dataset and rights, software versions, hardware, precision, batch size, sequence/context length, operator coverage, numerical tolerance, and resource budget. For adaptation also record trainable parameters, optimizer, checkpointing, sharding, and an agreed quality threshold.

Use one inference recipe first. Add one LoRA/QLoRA recipe if time and resources permit. Avoid general training claims from a single recipe.

## Human responsibilities

The team specifies candidate architectures and acceptance criteria, reviews model assumptions, interprets results, revises the design, and selects the next engineering step.

## Proposed agent responsibilities

Specialists may collect and cross-check sources, run team-specified calculations and benchmark jobs, check memory and communication assumptions, and request independent verification of conflicting results. Preserve inputs, outputs, source references, tool versions, and disagreements in versioned artifacts.

This is a proposed workflow, not an existing agent system.

## Deterministic checks to implement

- Memory footprint: weights, KV cache, runtime overhead, activations, gradients, and optimizer state as applicable.
- Compute and memory rooflines with explicit assumptions and units.
- Communication volume, endpoint directionality, latency, and contention assumptions.
- Constraint violations and sensitivity to uncertain inputs.
- Prediction error against small reference measurements on available hardware.

Measurements on existing hardware validate reference recipes and help assess modeling assumptions. They do not directly validate a proposed unfabricated chip.

## Collective comparison

Compare a coordinated specialist collective, a single-agent workflow, and isolated specialists using the same human-defined configurations, tools, sources, numerical checks, and resource budget.

Report calculation accuracy, missed constraint violations, reproducibility, traceability, prediction error where reference measurements exist, model/tool calls, and wall time. Show whether cross-agent checks changed a conclusion. Do not infer collective benefit merely from having multiple agents.

## Results publication gate

Publish commands, input manifests, environment details, result files, failure cases, and limitations with each result commit. Keep measured values, analytical estimates, simulated values, and design targets distinguishable. Only describe a component as implemented after its runnable artifact is present and verified.
