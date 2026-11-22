<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PROTOTYPING — repository foundation
-->

# Validation

This checkout's repository foundation is under qualification. Another repository's tests or coverage do not qualify it.

**Not qualified here:**
- intake;
- conversion;
- partition;
- interconnect;
- run;
- capture;
- co-emulation;
- any board or bitstream.

## Maintained scope

**What is enrolled.** The Python tools and their dedicated tests are enrolled in:
- Ruff and formatting;
- strict mypy;
- native NumPy-style documentation;
- statement coverage and branch coverage.

**The target.** Full meaningful coverage of every maintained source file.

**The tests.** The repository controls have public entry points, with success and refusal tests.

## Local and CI entry points

**Environment.** Use the selected interpreter and the hash locks in [Contributing](CONTRIBUTING.md).

**Named make targets.** They inspect their declared scopes.

**Full runs.** Full `make ci` and `make preflight` belong in CI, or in an admitted pre-push environment.

**Partial preflight.** A named partial preflight records its omitted checks as not run. It cannot clear acceptance as a whole.

**Public CI.** CI for this public repository runs on public material only.

## Evidence limits

- **Equivalence.** A bounded proof is not an equivalence. A simulation pass is not a proof.
- **Figures.** A tool estimate is not a measurement. One board unit's measurement says nothing about a population.
- **Workflows.** A static workflow check is not hosted execution.

**No guarantees of the following** follow from the maintained repository controls:
- prototype fidelity;
- timing;
- a physical result;
- a release;
- a DOI;
- hosted acceptance.
