<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No intake, conversion, partition, interconnect, run, capture or co-emulation component is implemented. The metadata keeps domain capabilities, claims and qualified formats empty.

## Intended data flow

1. **Intake.** It takes one design view, pinned by source, file list and elaboration digests. RTL that arrives outside such a view is refused.
2. **Conversion.** It maps every ASIC leaf, clock gate and multi-port memory to its FPGA substitute, with the evidence for each. Its input digests must equal the intake's.
3. **Partition.** It cuts the converted netlist across the FPGAs of one board profile. Each FPGA gets a fit report, and the engine's version, seed and input digest are pinned.
4. **The interconnect plan.** It declares:
   - every inter-FPGA link and its multiplexing ratio;
   - the clock-domain crossing framing;
   - the latency map;
   - the achieved prototype clock;
   - an equivalence check of the partitioned design against the single converted netlist.
5. **Runs.** A run records its mode, emulation or prototype, and for every phase whether it was virtual, built or physical.
6. **Debug captures.** Each capture maps back to the original RTL signal names on the lab timebase.

## Ownership

**This project owns** the seven prototyping records and the rules above.

**Other projects own:**

| What | Owner |
|---|---|
| contracts, operation profiles and the approval kernel | Circuit Core |
| board, toolchain and technology profiles | Circuit Technology |
| RTL, formal verification and synthesis | Circuit Digital |
| run plans and dispatch | Circuit Flow |
| timebase and bring-up | Circuit Lab |
| acceptance plans and sign-off | Circuit Acceptance |
| the grader bundles that may judge prototype fit | Circuit Learning |

**Instruments:** they seal, capture and compare evidence through their own registered interfaces.

## Interpretation

- A converted or partitioned design is a prototype of the chip, never the chip.
- A tool's utilisation and timing figures are estimates for the named part, corner and seed.
- A measured figure belongs to one serial-numbered board unit.
- A board's functional verdict counts mismatches against a reference trace and vector set fixed before the run, over every declared vector; it covers those vectors, not every input.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records and their fields.
