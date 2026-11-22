<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Circuit Prototyping

Circuit Prototyping is being built to turn one pinned chip design into FPGA emulation and prototype runs whose evidence can be checked afterwards. That evidence covers the design taken in, every substitution made for the FPGA, the partition across FPGAs, the links between them, the run itself, the debug captures and the host side of a hybrid run.

**What this checkout holds:** repository validation tooling and documentation only. Full foundation qualification is in progress.

There is no intake, conversion, partition or run command, no registered record format, and no board, bitstream or prototype run.

## Boundary

This project owns the planned prototyping records:
- design intake;
- ASIC-to-FPGA conversion;
- partition;
- inter-FPGA interconnect;
- prototype run;
- debug capture;
- host co-emulation binding.

**What it imports:** only Circuit Core and Circuit Technology.

**What it reads but does not own:**

| Repository | What this project takes from it |
|---|---|
| Circuit Technology | board and toolchain profiles |
| Circuit Digital | RTL, formal results and synthesis |
| Circuit Flow | run plans |
| Circuit Lab | timebase association and bring-up |
| Circuit Acceptance | acceptance plans |

These are read as records, never as code imports.

**Instruments it registers with:**
- Loop Timing Witness, Spike Log, Sim-Real Witness and Bitstream Evidence CI;
- Evidence Manifest Toolkit, which supplies shared evidence operations.

SC-NeuroCore's existing board flows move here when the split plan reaches them.

**What a prototype is not:**
- **It is not the chip.**
- **A stand-in is a substitution, never an equivalent.** This covers an FPGA stand-in for a physical entropy source or for a memory PHY.
- **An encrypted third-party block stays a black box.** Only its vendor's flow processes it, and no open-flow claim is made about it.
- **Fit and timing figures are tool estimates, not measurements.**
- **Real-time claims need native rate.** An interface that runs below its native rate is time-scaled, and it supports no real-time claim.
- **One board unit supports no population or yield statement.**
- **"Equivalent" needs an unbounded proof.** It is stated only on such a proof. A bounded proof is stated with its depth.

## Current tooling

**The repository controls.** They inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and the inventory;
- preflight orchestration.

**The metadata.** It declares architecture-only maturity, and its domain capability and claim inventories are empty.

**How to run them.**
- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the scope.

## Intended evidence

A run record will name, for every phase, whether that phase was virtual, built or physical. It will bind:
- the bitstream evidence;
- the firmware;
- the captured streams;
- the toolchain identity.

**Hybrid runs.** A hybrid run also binds its host-side transactors and virtual-platform models, by digest.

**Physical runs.** A physical run is an evaluation under conditions declared beforehand: temperature, voltage, clock, the number of trials and the acceptance rule. It is never a training reward.

**Formats.** None of these formats is registered or qualified by this foundation.

## Documentation and support

Read:
- [Architecture](ARCHITECTURE.md);
- [support](SUPPORT.md);
- [security reporting](SECURITY.md);
- [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a board, a performed run or a measured figure.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
