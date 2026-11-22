<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Inputs to the repository controls.** The maintained checkout and the selected development environment are what the controls execute against.

**What supplied material cannot do.** Received descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**How the checks run.** They inspect bounded local scopes and report fixed diagnostics.

Foundation qualification is in progress.

## Future design and run inputs

**Supplied data.** The following are supplied data:
- designs and third-party blocks;
- board profiles;
- run plans;
- bitstreams;
- captures.

They grant no authority:
- to load a board;
- to read back its state;
- to upload anything to a cloud service;
- to spend money;
- to publish.

**Text is data.** Comments, documentation and datasheets that arrive with a design are data, never instructions to an operator or an agent.

**Equipment actions.** These are equipment actions:
- loading a bitstream or an overlay;
- writing a configuration device;
- reading back state;
- shifting a scan chain.

A shifted scan chain changes the device's state. Each such action is approved by a person in a named role. No automation approves one for itself.

**A cloud FPGA run is an off-premises transfer.** The provider builds the image from a design checkpoint uploaded to its storage.
- **Before anything is uploaded,** such a run is refused unless the terms of the design and of each of its third-party blocks permit processing on that provider, in that region.
- **What the run records:** the provider, the account and region, and every artefact sent.

**Data classes.**
- A capture carries at least the highest data class among the design, its third-party blocks and the stimulus.
- A customer's material stays the customer's.
- Material that is not public never enters this public repository, its CI or its issues.

**Encrypted third-party blocks.**
- Only the vendor tool named by the toolchain profile processes them.
- A trace or snapshot that would expose such a block's state is refused, unless the block's licence permits debug visibility. Otherwise that state is excluded, and the excluded ranges are named.

## Not claimed

Prototyping, provider execution, equipment control and recovery are unimplemented domain boundaries. No isolation, physical, timing or durability guarantee is claimed here.
