<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Decision: keep FPGA prototyping apart from digital design, flow scheduling and sign-off

## Context

An FPGA prototype changes the design it runs:
- **Substitution.** Clock gates, memories and physical sources are replaced.
- **Partition.** The design is cut across devices.
- **Links.** Multiplexed links between devices add latency.
- **Rate.** External interfaces may run slower than their native rate.

A passing prototype run therefore cannot stand for the chip. Its figures cannot stand for measurements without their tool, part, corner, seed and board unit.

## Decision

**What Circuit Prototyping owns:** design intake, conversion, partition, interconnect, run, debug-capture and host co-emulation records.

**What it imports:** only Circuit Core and Circuit Technology.

**Owned elsewhere:**

| What | Owner |
|---|---|
| RTL, formal verification and synthesis | Circuit Digital |
| scheduling | Circuit Flow |
| lab timebase and bring-up | Circuit Lab |
| sign-off | Circuit Acceptance |

**Evidence instruments.** Sealing, capture and comparison stay with the evidence instruments, through their registered interfaces.

## Consequences

**What can be qualified now:** repository tooling, before any board exists.

**What it cannot qualify:** absent boards, bitstreams or runs.

**What domain support requires:**
- the pinned intake;
- complete substitution evidence;
- a pinned, reproducible partition;
- an equivalence result in its stated proof mode;
- declared run conditions;
- per-unit physical figures.

**Protected blocks and equipment.**
- Encrypted blocks stay black boxes.
- Equipment actions and cloud transfers remain decisions of a person in a named role.
