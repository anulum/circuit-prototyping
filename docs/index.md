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

This repository is preparing the records and rules that turn one pinned chip design into FPGA emulation and prototype runs whose evidence can be checked afterwards: design intake, conversion, partition, inter-FPGA links, runs, debug captures and the host side of hybrid runs. Its current executable surface is repository validation tooling. It has no intake, conversion, partition or run command, no registered record format, and no board, bitstream or prototype run.

Circuit Prototyping is part of the **SC Neuromorphic Computing Systems** group (SC-NEUROMORPHIC-COMPUTING-SYSTEMS). The [group and project map](https://github.com/anulum/sc-neurocore/blob/main/docs/ecosystem.md) shows the whole programme and where this repository sits in it.

A prototype is not the chip. Stand-ins are substitutions, never equivalents; fit and timing figures are tool estimates; "equivalent" is stated only on an unbounded proof; and a measured figure belongs to one serial-numbered board unit.

Read [Architecture](ARCHITECTURE.md), [validation tooling](validation-tooling.md), [data boundaries](THREAT_MODEL.md) and the [repository boundary decision](adr/0001-repository-boundary.md).
