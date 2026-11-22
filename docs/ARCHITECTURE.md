<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared scope.

**What received metadata cannot do:** select another policy or grant prototype evidence.

Foundation qualification is in progress.

## Intended prototyping boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Design intake | One pinned design view; its third-party blocks; the licence terms for each block | Source, file list and elaboration digests. For every third-party block: whether its terms permit processing on cloud hosts, and in which regions. Encrypted blocks are marked |
| Conversion manifest | Every ASIC-to-FPGA substitution | For each converted block: a formal proof, a simulation reference or the vendor flow's own report. Stand-ins for physical entropy sources and memory PHYs are declared as substitutions |
| Partition manifest | The cut across the FPGAs of one board profile | The partition engine's version, its seed and the input netlist digest. Per-FPGA utilisation and timing as named tool estimates |
| Interconnect plan | Inter-FPGA links, multiplexing, clock-domain crossings and external interfaces | Each link's algorithm and achieved ratio; a per-path latency map; the partition equivalence result with its proof mode; native and prototype rates for every external interface |
| Prototype run record | One run, emulation or prototype, with a virtual, built or physical class for each phase | Bitstream evidence, firmware, captured streams and toolchain identity. For physical runs: the declared conditions, trials and acceptance rule, and the board's serial number |
| Debug capture record | Trace windows and state snapshots | Mapping back to the RTL signal names; method and cycle; state digest; replay request; any excluded protected ranges |
| Host co-emulation binding | The host side of a hybrid run | Transactor set and virtual-platform models by digest; virtual-clock semantics; matching register-map digests; every boundary transaction time-stamped |

## Proof modes

**What each verdict requires:**
- **"Equivalent"** is stated only after an unbounded proof, by k-induction or PDR.
- **"Equivalent up to depth k"** is the verdict for a bounded proof, and it names its depth.
- **"Not equivalent"** keeps its counterexample trace.

**Exact mode.** The partitioned design is decoupled into latency-insensitive, token-based channels. It is then cycle-exact by construction, and identical cycle-level output is required.

**Fast mode.** It maps latency instead, and states that mapping.

## Licence isolation

| Tool | Licence | How it runs |
| --- | --- | --- |
| TritonPart, part of OpenROAD | BSD-3-Clause | may run in process |
| KaHyPar | GPL-3.0 | separate process |
| QEMU | GPL-2.0 | separate process; its device models attach across that boundary, and no project code is linked into it |
| SystemC | Apache-2.0 | may be linked |

**Before a tool is installed or run,** its licence is read and admitted.

## Planned record schemas

- `circuit_prototyping.design_intake_record.v1`
- `circuit_prototyping.conversion_manifest.v1`
- `circuit_prototyping.partition_manifest.v1`
- `circuit_prototyping.interconnect_plan.v1`
- `circuit_prototyping.prototype_run_record.v1`
- `circuit_prototyping.debug_capture_record.v1`
- `circuit_prototyping.host_coemulation_binding.v1`

These are planned names. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
